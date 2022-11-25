개요

  

![](https://t1.daumcdn.net/cfile/tistory/99BAEF3359FFBFEC12)

Piwigo는 PHP 기반 갤러리 프로그램이에요. 얘를 설치하게 되면 인터넷으로 사진을 관리할 수 있어요. 사진마다 댓글도 달거나, 사진/앨범 별로 접근 제한을 두거나, 원하는 사진이나 앨범을 공유할 수도 있구요.

도메인을 주게 되면 나만의 갤러리로 쉽게 접근할 수 있으니까, 주변 사람들에게 자랑하고 싶은 사진을 보여주고 싶을 때, 부모님이나 친척들에게 행복한 사진들을 보여주고 싶을 때 좋아요.

사실 웹 기반 갤러리 프로그램이 꼭 필요한 건 아니에요. h5ai 같은 걸 깔면 사진이 웹에서 Preview가 되긴 해요. Seafile, NextCloud 등 클라우드 앱도 있고, 기타 기기에선 DLNA를 사용해도 되구요. 하지만 역시 간단하면서 전문적인 갤러리 프로그램이 필요할 때가 있어요.

Piwigo 설치가 조금 복잡할 수 있어요. 하지만 복붙만으로도 설치하실 수 있게끔 정리해 놓을테니 잘 따라와주세요 :) 아, 우분투 기준이고 Nginx + PHP7.1 + MySQL(MariaDB)가 설치되어 있어야 해요.

  

설치 준비

  

미리 Piwigo를 위한 데이터베이스가 준비되어 있어야 해요. 아래 명령어를 통해 데이터베이스와 사용자를 만들어주세요.

```bash
mysql -u root -p
```

```sql
CREATE DATABASE `piwigo-db`;
CREATE USER 'piwigo'@'localhost' IDENTIFIED BY 'password-here';
GRANT ALL PRIVILEGES ON `piwigo-db`.* TO 'piwigo'@'localhost' IDENTIFIED BY 'password-here';
FLUSH PRIVILEGES;
```

기본 업로드 디렉토리가 좀 이상하게, 웹 소스 프로젝트 디렉토리 안에 있어요. 웹에서도 설정할 수 없구요. 사진이 몇 장 없으면 괜찮겠지만 사용할수록 루트 디렉토리의 용량이 부족해질 거에요.

하드디스크가 마운트된 디렉토리로 옮기기 위해, 미리 디렉토리를 만들어 둘게요. 여기선 **/media/nas/piwigo_upload** 로 하겠습니다.

```bash
sudo mkdir /media/nas/piwigo_upload
chmod 777 /media/nas/piwigo_upload

# Change written group name to yours. If you haven't any group for using nas, type both user/group name as 'www-data'.
chown www-data:nas /media/nas/piwigo_upload
```

마지막으로 **php-gd** 모듈을 다운받을게요.

```bash
sudo apt install php7.1-gd
```

  

Piwigo 설치

  

wget 명령어를 통해 최신 Piwigo 패키지를 받아주세요.

```bash
wget -O piwigo_latest.zip http://piwigo.org/download/dlcounter.php?code=latest
```

그리고 웹 기반 프로그램이기 때문에 **/var/www** 경로 아래에 압축을 풀도록 할게요.

```bash
sudo unzip -d /var/www piwigo_latest.zip
```

Nginx에서 실행할 수 있도록 소유권을 **www-data**로 바꿔줄게요.

```bash
sudo chown -R www-data:www-data /var/www/piwigo
```

업로드 디렉토리를 방금 만든 곳으로 바꿔줄게요. 기존 업로드 디렉토리를 지우고 **소프트 링크**를 생성해요.

```bash
sudo rmdir /var/www/piwigo/upload
sudo ln -s /media/nas/piwigo_upload /var/www/piwigo/upload
```

이제 Nginx 서버 설정을 해줄게요. 새로운 서버 설정 파일을 하나 만들면 돼요.

```bash
sudo vi /etc/nginx/sites-available/piwigo
```

아래 내용을 복붙해주세요. 포트는 임시로 8282 번으로 하겠습니다.

```nginx
server {
    listen 8282;
    listen [::]:8282;

    root /var/www/piwigo;

    index index.php;

    server_name _;

    location / {
            try_files $uri $uri/ =404;
    }

    # This option is important for using PHP.
    location ~ \.php$ {
            include snippets/fastcgi-php.conf;
            fastcgi_pass unix:/var/run/php/php7.1-fpm.sock;
    }
}
```

활성화 후 Nginx를 다시 로드할게요.

```bash
sudo ln -s /etc/nginx/sites-available/piwigo /etc/nginx/sites-enabled/piwigo
sudo service nginx reload
```

이제 웹에서 NAS IP와 포트 번호로 접속하면 아래처럼 설치 페이지가 떠요.

![](https://t1.daumcdn.net/cfile/tistory/99831D3359FFCCE624)

만들어둔 데이터베이스 정보와 적절한 관리자 계정 정보를 입력하고 설치하세요.

  

테스트

  

wallpapers 라는 앨범을 만들어 136개의 이미지 파일을 올려볼게요.

![](https://t1.daumcdn.net/cfile/tistory/99C3AB3359FFD76013)

![](https://t1.daumcdn.net/cfile/tistory/9961413359FFD76D07)

잘 올라갔나 확인해볼까요?

![](https://t1.daumcdn.net/cfile/tistory/99AE783359FFD77D38)

서버 내 하드디스크에도 잘 올라갔네요 :)

![](https://t1.daumcdn.net/cfile/tistory/99C5033359FFD78A1E)

  

여담

  

설치는 어렵지 않았지만, 경로 설정 때문에 여러 설정 파일을 고쳐보는 등 여러가지 시도해봤네요.. 소프트 링크가 가장 안전하고 확실하고 쉬운 방법인 것 같아요 :)

여러 테마도 설치하고, 도메인도 주고 SSL도 먹여서 앨범을 공유하세요.

OMV에서도 비슷하게 하시면 되는데, Nginx 서버 설정을 OMV 웹에서 하시면 돼요.

  

참고

  

-   [http://piwigo.org/basics/installation_manual](http://piwigo.org/basics/installation_manual)