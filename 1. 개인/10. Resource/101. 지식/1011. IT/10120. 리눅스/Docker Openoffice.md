
1. Docker 설치 
    - 레드햇 도커 설치
2. 도커 서비스 런
3. 도커 루트 경로 변경
4. 레드햇 git 설치
5. Docker compose 설치
 마지막 compose up --> su root 로 변경해서 해줘야 함


docker exec -it mariadb-server service mariadb start


create user 'greatbps'@'%' identified by 'killer99!!';


CREATE USER 'greatbps'@'%' IDENTIFIED BY 'killer99!!';


grant all privileges on *.* to 'testId1'@'loalhost';




$CONFIG = array (
  'memcache.local' => '\\OC\\Memcache\\APCu',
  'apps_paths' =>
  array (
    0 =>
    array (
      'path' => '/var/www/html/apps',
      'url' => '/apps',
      'writable' => false,
    ),
    1 =>
    array (
      'path' => '/var/www/html/custom_apps',
      'url' => '/custom_apps',
      'writable' => true,
    ),
  ),
  'instanceid' => 'ocmgytoyy8kl',
  'passwordsalt' => '7Vm08a1E4iLWDBRn8HNNciaMfVSfwy',
  'secret' => 'CkaCL87oo5a9miUORMC/S6nnzUqnIL1PFQHLJWpG2Vp4QW1M',
  'trusted_domains' =>
  array (
    0 => '192.168.123.100',
    1 => '*',
    2 => 'great.ddns.net',
    3 => 'nginx-server',
  ),
  'datadirectory' => '/var/www/html/data',
  'dbtype' => 'mysql',
  'version' => '27.1.1.0',
  'overwrite.cli.url' => 'http://192.168.123.100',
  'dbname' => 'nextcloud',
  'dbhost' => '192.168.123.100',
  'dbport' => '',
  'dbtableprefix' => 'oc_',
  'mysql.utf8mb4' => true,
  'dbuser' => 'oc_greatbps',
  'dbpassword' => ';@4sA]3t-#hW/Ge4H:IK1%qn<DP5+X',
  'installed' => true,
  'onlyoffice' =>
  array (
    'DocumentServerUrl' => '/ds-vpath/',
    'DocumentServerInternalUrl' => 'http://onlyoffice-document-server/',
    'StorageUrl' => 'http://nginx-server/',
    'jwt_secret' => 'secret',
  ),
);



ersion: '3'
services:
  db:
    container_name: mariadb-server
    image: mariadb
    command: --transaction-isolation=READ-COMMITTED --binlog-format=ROW
    restart: always
    ports:
      - 3306:3306
    volumes:
      - mysql_data:/var/lib/mysql
    environment:
      - MYSQL_ROOT_PASSWORD=killer99!!
      - MYSQL_PASSWORD=killer99!!
      - MYSQL_DATABASE=nextcloud
      - MYSQL_USER=greatbps
  app:
    container_name: app-server
    image: nextcloud:fpm
    restart: always
    expose:
      - '80'
      - '9000'
    volumes:
      - app_data:/var/www/html
  onlyoffice-document-server:
    container_name: onlyoffice-document-server
    image: onlyoffice/documentserver:latest
    restart: always
    environment:
      - JWT_SECRET=secret
    expose:
      - '80'
      - '443'
    volumes:
      - document_data:/var/www/onlyoffice/Data
      - document_log:/var/log/onlyoffice
  nginx:
    container_name: nginx-server
    image: nginx
    restart: always
    ports:
      - 80:80
      - 443:443
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
      - app_data:/var/www/html
volumes:
  document_data:
  document_log:
  app_data:
  mysql_data:



```
docker volume create --name USB_2TB --opt type=none --opt device=/mnt/USB_2TB/vin --opt o=bind
```


docker volume create --name  mysql_data --opt type=none --opt device=/data/docker --opt o=bind



/var/www/html/data/USB_2TB
/var/www/html/data/greatbps/files/USB_2TB

sudo chown -R www-data:www-data  /mnt/USB_2TB/vin/data/docker
sudo chmod -R 0750 /mnt/USB_2TB/vin/data/docker

sudo chown -R www-data:www-data /var/www/html/data/greatbps/files/USB_2TB
sudo chmod -R 0750 /var/www/html/data/greatbps/files/USB_2TB


kkiller99!!
docker run -d -p 8080:8080 -v first-volume-data:/container-path-1 -v second-volume-data:/container-path-2:ro --name web-app web-app:latest

nextcloud:fpm


      - app_data:/var/www/html
      - USB_2TB:/var/www/html/data/USB_2TB
  - docker cp hostFilePath container_name:containerPath
  - docker cp -r /mnt/USB_2TB/vin/99.Personnel/01.Vincent app-server:/var/www/html/data/greatbps/files/USB_2TB


```json
{
    "graph": "/mnt/docker-data",
    "storage-driver": "overlay"
}
```


docker images -a


docker stop -t 300 storagenode 
docker rm storagenode
docker logs --tail 20 storagenode


```
docker run \
    -v ./db-data/postgres/:/var/lib/postgresql/data/ \
    --entrypoint /bin/chown \
    postgres:15.0 -Rc postgres:postgres /var/lib/postgresql/data
```



/dev/sda1 /mnt/USB_2TB  ntfs  defaults,uid=1000,gid=1000,rw 0 0  => 폐기
UUID=01CEB39DC89C0AB0 /mnt/USB_2TB  ntfs rw,noauto 0 0


 LABEL="NFS" UUID="01CEB39DC89C0AB0" TYPE="ntfs" PARTUUID="c10a8299-01"
sudo dnf install autofs