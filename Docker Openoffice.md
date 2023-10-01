
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



