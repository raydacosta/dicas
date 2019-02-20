
// verificasr tamanho dos arquivos
sudo du -sh * 2>/dev/null | sort -h

/etc/init.d/sshd restart

sudo service ssh restart

who


---------------------------------------------------------------------------------------

Porta - USB

sudo ls -l /dev/tty*
/dev/ttyACM0
/dev/ttyACM0


1a2c:0e24
SUBSYSTEMS=="usb", ATTRS{idVendor}=="1a2c", ATTRS{idProduct}=="0e24", MODE=="0777"

---------------------------------------------------------------------------------------

Mais um jeito de achar arquivos grandes
sudo find . -size +500M
sudo find . -size +1G
sudo du -hs *
sudo find / -name '*kswap_svc*'


---------------------------------------------------------------------------------------
Descobrir portas sendo usadas
sudo netstat -tlpn | grep 8080
lsof -i -Pn

---------------------------------------------------------------------------------------


​SELECT table_name MDWCloud_ArquivoEntity, data_length / 1024 / 1024 "Tamanho da tabela em MB", index_length / 1024 / 1024 "Tamanho do indice em MB", engine FROM information_schema.TABLES WHERE table_name like 'MDWCloud_ArquivoEntity';​


ssh -i /home/raydacosta/sshccrr.ppk ccrr@104.197.48.27




---------------------------------------------------------------------------------------



update Romaneio set status = 'Criado' , totalrealizado = 0, SYNCRONIZADOR = 0  where numerolote = '384286';
delete  FROM Caixa where idObjetoExtgerno  = '384286'   
update Item set status = 'Criado' , SYNCRONIZADOR = 0 , Caixa_ir   = 0  where Caixa_ir  != 0  and numeropedido = '384286'

---------------------------------------------------------------------------------------








---------------------------------------------------------------------------------------
sudo apt-get install python-software-properties
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java6-installer
sudo apt-get install oracle-java7-installer
sudo apt-get install oracle-java8-installer

sudo update-alternatives --config java
----------------------------------------------------------------------------------------
urljdk: 
/usr/lib/jvm/java-6-oracle
/usr/lib/jvm/java-7-oracle

----------------------------------------------------------------------------------------
gerar wsdl
cd /home/ubuntu/weboksite/jaxws-ri/bin
./wsimport.sh -verbose -d /home/ubuntu/weboksite/sources -wsdl http://190.52.112.51:8080/IntrawayWS/server.php?wsdl

----------------------------------------------------------------------------------------
setar avariavel no linux
export JAVA_HOME=/usr/lib/jvm/java-6-oracle
export PATH=$JAVA_HOME/bin:$PATH

export AXISCLASSPATH="/home/raydacosta/work/axis-1_4/lib/axis.jar;/home/raydacosta/work/axis-1_4/lib/axis-ant.jar;/home/raydacosta/work/axis-1_4/lib/commons-discovery-0.2.jar;/home/raydacosta/work/axis-1_4/lib/commons-logging-1.0.4.jar;/home/raydacosta/work/axis-1_4/lib/jaxrpc.jar;/home/raydacosta/work/axis-1_4/lib/log4j-1.2.8.jar;/home/raydacosta/work/axis-1_4/lib/saaj.jar;/home/raydacosta/work/axis-1_4/lib/wsdl4j-1.5.1.jar"
export PATH=$AXISCLASSPATH


export JAVA_HOME="/usr/lib/jvm/java-7-oracle"
export PATH=$PATH:/usr/lib/jvm/java-7-oracle
echo $JAVA_HOME



pligin rpc netbeans
Go to Tools -> plugins -> Settings -> Add and set URL as
http://deadlock.netbeans.org/hudson/job/nbms-and-javadoc/lastStableBuild/artifact/nbbuild/nbms/updates.xml.gz
http://deadlock.netbeans.org/hudson/job/nbms-and-javadoc/lastStableBuild/artifact/nbbuild/nbms/updates.xml.gz

plugin axis
https://www.youtube.com/watch?v=4RPCb-KCKs4 - Video de exemploq  mostrar como usar
http://deadlock.netbeans.org/hudson/job/nbms-and-javadoc/lastStableBuild/artifact/nbbuild/nbms/updates.xml.gz 
./wsdl2java.sh -o /home/raydacosta/work/resource -p com.raysystem.integracao.infraway -s http://190.52.112.51:8080/IntrawayWS/server.php?wsdl
./wsdl2java.sh -o '/home/raydacosta/work/resource' -p 'com.raysystem.integracao.infraway' -s 'http://190.52.112.51:8080/IntrawayWS/server.php?wsdl'

./wsdl2java.sh -o '/home/raydacosta/work/resource' /home/raydacosta/work/server.wsdl


java org.apache.axis.wsdl.WSDL2Java -o '/home/raydacosta/work/resource' -s -S true -p com.raysystem.integracao.infraway 'http://190.52.112.51:8080/IntrawayWS/server.php?wsdl'


java -cp ".;/home/raydacosta/work/axis-1_4/lib/axis.jar;/home/raydacosta/work/axis-1_4/lib/axis-ant.jar;/home/raydacosta/work/axis-1_4/lib/commons-discovery-0.2.jar;/home/raydacosta/work/axis-1_4/lib/commons-logging-1.0.4.jar;/home/raydacosta/work/axis-1_4/lib/jaxrpc.jar;/home/raydacosta/work/axis-1_4/lib/log4j-1.2.8.jar;/home/raydacosta/work/axis-1_4/lib/saaj.jar;/home/raydacosta/work/axis-1_4/lib/wsdl4j-1.5.1.jar" org.apache.axis.wsdl.WSDL2Java -o '/home/raydacosta/work/resource' -s -S true -p com.raysystem.integracao.infraway 'http://190.52.112.51:8080/IntrawayWS/server.php?wsdl'

----------------------------------------------------------------------------------------


Mudar a versão do Java no ubuntu
update-alternatives --config java

sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.5.0_22/bin/java" 4
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.5.0_22/bin/javac" 4
sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/lib/jvm/jdk1.5.0_22/bin/javaws" 4
sudo chown -R root:root /usr/lib/jvm/java5/jdk1.5.0

export JAVA_HOME=/usr/lib/jvm/java5/jdk1.5.0
export PATH=$JAVA_HOME/bin:$PATH


JAX-RPC Web Services
wsimport -keep  -d /home/raydacosta/work/resource http://190.52.112.51:8080/IntrawayWS/server.php?wsdl

encontrar ip publico em um servidor
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'


----------------------------------------------------------------------------------------

Configurando acesso remoto em servidores MySQL
sudo nano /etc/mysql/my.cnf
bind-address  =  127.0.0.1 
sudo /etc/init.d/mysql restart
mysql -uroot -p[senha]
GRANT ALL ON *.* TO 'root'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;

Caso queira conceder acesso a uma máquina específica da rede:
mysql> GRANT ALL ON *.* TO 'root'@'[ip da máquina]' IDENTIFIED BY '[senha]' WITH GRANT OPTION;

systemctl status mysql.service
mysqladmin -p -u root version

FLUSH PRIVILEGES;

caso queira testar a conexão, execute esse comando em uma máquina cliente da rede:
$ mysql -uroot -p[senha] -h[IP do servidor]

REMOVER MYSQL
sudo dpkg --configure -a
sudo rm -rf /var/lib/dpkg/info/a.*
sudo apt-get remove --purge mysql*
sudo apt-get autoremove
sudo apt-get autoclean
sudo apt-get clean


update-alternatives: a usar 
/etc/mysql/my.cnf.fallback para disponibilizar 
/etc/mysql/my.cnf (my.cnf) em modo auto


sudo apt-get -f install
sudo apt-get -f remove

stop mysql
sudo /etc/init.d/mysql stop
sudo /etc/init.d/mysql restart
sudo /etc/init.d/mysql start


parametros
mysqld --verbose --help

sudo apt-get update
sudo apt-get install mysql-server mysql-client
sudo mysql_secure_installation
sudo mysql_install_db



sudo mysqld_safe --skip-grant-tables


----------------------------------------------------------------------------------------

GRANT ALL ON *.* TO 'root'@'%' IDENTIFIED BY '[senha]' WITH GRANT OPTION;

mkdir /home/informatica/MDWCloud/embalagem
mkdir /home/informatica/MDWCloud/coleta
mkdir /home/informatica/MDWCloud/carga
mkdir /home/informatica/MDWCloud/wms

mkdir /home/informatica/MDWCloud/embalagem/bkp
mkdir /home/informatica/MDWCloud/coleta/bkp
mkdir /home/informatica/MDWCloud/carga/bkp
mkdir /home/informatica/MDWCloud/wms/bkp


chmod 777 /home/informatica/MDWCloud/embalagem
chmod 777 /home/informatica/MDWCloud/coleta
chmod 777 /home/informatica/MDWCloud/carga
chmod 777 /home/informatica/MDWCloud/wms

chmod 777 /home/informatica/MDWCloud/embalagem/bkp
chmod 777 mkdir /home/informatica/MDWCloud/coleta/bkp
chmod 777 mkdir /home/informatica/MDWCloud/carga/bkp
chmod 777 mkdir /home/informatica/MDWCloud/wms/bkp

sudo mount -t cifs //192.168.1.2/Arquivos/portal/embala/producao /home/informatica/MDWCloud/embalagem
sudo mount -t cifs //192.168.1.2/Arquivos/portal/expede/coleta /home/informatica/MDWCloud/coleta
sudo mount -t cifs //192.168.1.2/Arquivos/portal/carga /home/informatica/MDWCloud/carga
sudo mount -t cifs //192.168.1.2/Arquivos/portal/wms /home/informatica/MDWCloud/wms

sudo umount /home/informatica/MDWCloud/embalagem
sudo umount /home/informatica/MDWCloud/coleta
sudo umount /home/informatica/MDWCloud/carga
sudo umount /home/informatica/MDWCloud/wms


Runtime rt = Runtime.getRuntime();
Process proc;
proc = rt.exec("gksudo umount /mnt/web");
proc = rt.exec("gksudo mount -t cifs -o rw,username=fred,workgroup=mshome //fredserver/web /mnt/web");


URI uri = new URI("smb://192.168.1.2/Arquivos/portal/embala/producao");
File f = new File(uri);

----------------------------------------------------------------------------------------

== DESABILITAR LOG DO JBOSS ==

/jboss-4x/server/default/conf/jboss-log4j.xml

  <category name="com.arjuna">
    <priority value="ERROR"/>
  </category>

         <category name="org.jboss">
         <priority value="ERROR"/>
         </category>

         <category name="log4j.logger.net.sf.hibernate">
         <priority value="ERROR"/>
         </category>

         <category name="net.sf.hibernate">
        <priority value="ERROR"/>
         </category>

         <category name="org.core.hibernate">
         <priority value="ERROR"/>
         </category>

         <category name="org.hibernate.engine.TwoPhaseLoad">
         <priority value="ERROR"/>
         </category>


         <category name="org.hibernate.jdbc.AbstractBatcher">
         <priority value="ERROR"/>
         </category>


         <category name="org.hibernate.SQL">
         <priority value="ERROR"/>
         </category>

         <category name="org.hibernate.loader.Loader">
         <priority value="ERROR"/>
         </category>


         <category name="org.hibernate">
         <priority value="ERROR"/>
         </category>





----------------------------------------------------------------------------------------

Para fazer jogos em android
https://www.scirra.com
https://unity3d.com/pt/learn/live-training

----------------------------------------------------------------------------------------
Acessar amazon
ssh -i KeypairJerico2.pem ubuntu@54.94.246.192

----------------------------------------------------------------------------------------
Assinatura de jars
//url de certificados validdo
http://timestamp.verisign.com
http://tsa.starfieldtech.com
https://timestamp.geotrust.com/tsa

ASSINAR ARQIVOS
jarsigner -tsa http://timestamp.digicert.com -keystore /home/raydacosta/Dropbox/PROJETOS/DOCS/CertificadoCCRR/CCRR.jks -storepass sucess@753 -keypass sucess@753  -verbose /home/raydacosta/Dropbox/PROJETOS/SOURCES/NETBEANS/MDWCloud2.0/MDWIdentificacao/dist/MDWIdentificacao.jar CCRR


=====================================================================================================================
COMANDOS LINUX
=====================================================================================================================

São elas:

    USER :: Login do proprietário do processo.
    PID :: Identificador do processo.
    %CPU :: Porcentagem de CPU utilizada pelo processo.
    %MEM :: Porcentagem de memória virtual utilizada pelo processo.
    VSZ :: Virtual Size. Tamanho do processo em Kbytes.
    RSS :: Número de páginas de 1 Kbyte na memória.
    TTY :: Identificador do terminal que controla o processo.
    STAT :: Estado atual do processo.
    START :: Horário em que o processo foi iniciado.
    TIME :: Tempo de processamento utilizado pelo processo.
    COMMAND :: Comando utilizado para iniciar o processo.


Alguns exemplos de uso do comando ps, são:
1. Exibir processos associados a um terminal:
# ps -a
2. Exibir todos os processos iniciados pelo usuário:
# ps -u usuario
3. Exibir processos não associados a nenhum terminal:
# ps -x

----------------------------------------------------------------------------------------

O comando pstree:

Este comando permite ver os processo em execução em forma de árvore. Alguns exemplos de seu uso, são:
1. Exibir os processo em execução e os comandos usados para executá-los:
# pstree -a
2. Exibir os processos em execução e os Process Identifier (PID) dos mesmos:
# pstree -p

O comando pidof:
Todo processo possui um número identificador, este número é chamado PID (process identifier, ou identificador de processo). Para descobrirmos qual é o PID de um determinado processo, utilizamos o comando pidof.

Exemplo de uso:
# pidof nomeProcesso


Os comandos kill, killall e xkill:
Estes comandos são utilizados para enviar sinais aos processos em execução. Alguns dos sinais básicos que podem ser enviados aos processos, são:
    STOP :: Pausa o processo.
    CONT :: Continua a execução de um processo pausado.
    SIGTERM :: Finaliza o processo elegantemente.
    KILL :: Finaliza o processo instantaneamente.

Comando kill:
Este comando envia um sinal para um processo, através de seu PID:
# kill -SINAL pid

Comando killall:
Este comando envia um sinal para um processo, através de seu nome:
# kill -SINAL nomeProcesso
Comando xkill:

Este comando transforma o ponteiro do mouse num X finalizador de processos. Permite finalizar um processo apenas clicando em sua janela:
# xkill

O comando top:
Este comando permite visualizar os processos em execução de forma dinâmica, assim como no comando ps. As informações mostradas por este comando, são divididas em colunas.
Estas colunas, são:
    PID :: PID do processo.
    USER :: Usuário que iniciou o processo.
    PR :: Prioridade no uso do processador.
    NI :: Niceness.
    VIRT :: A memória virtual é a memória de troca (SWAP).
    RES :: A memória física é a memória RAM.
    SHR :: Quantidade de memória alocada para o processo.


* Importante: um processo reserva uma quantidade de memória além do necessário para sua execução. Esta memória pode ser requisitada por outros processos, caso seja necessário.
Os processos possuem vários estados, são eles:

    D (Daemon) :: Processo aguardando operações E/S.
    R (Running) :: Processo em execução.
    S (Sleeping) :: Processo em estado de espera.
    T (Stopped) :: Processo parado ou suspendido.
    Z (Zombie) :: Iniciado por um processo já finalizado.

    %CPU :: Porcentagem de uso do processador naquele instante.
    %MEM :: Porcentagem de uso da memória naquele instante.
    TIME+ :: Tempo de uso do processador (pode ser impreciso).
    COMMAND :: Comando utilizado para iniciar o processo.


Exemplos de uso do comando top:
1. Monitorar todos os processos em execução:
# top
2. Monitorar processos de um determinado usuário:
# top -u usuario
3. Monitorar um único processo:
# top -p PID


=====================================================================================================================

Google Play services API 	Description in build.gradle
Google+ 	com.google.android.gms:play-services-plus:8.4.0
Google Account Login 	com.google.android.gms:play-services-auth:8.4.0
Google Actions, Base Client Library 	com.google.android.gms:play-services-base:8.4.0
Google Address API 	com.google.android.gms:play-services-identity:8.4.0
Google App Indexing 	com.google.android.gms:play-services-appindexing:8.4.0
Google App Invites 	com.google.android.gms:play-services-appinvite:8.4.0
Google Analytics 	com.google.android.gms:play-services-analytics:8.4.0
Google Cast 	com.google.android.gms:play-services-cast:8.4.0
Google Cloud Messaging 	com.google.android.gms:play-services-gcm:8.4.0
Google Drive 	com.google.android.gms:play-services-drive:8.4.0
Google Fit 	com.google.android.gms:play-services-fitness:8.4.0
Google Location, Activity Recognition, and Places 	com.google.android.gms:play-services-location:8.4.0
Google Maps 	com.google.android.gms:play-services-maps:8.4.0
Google Mobile Ads 	com.google.android.gms:play-services-ads:8.4.0
Mobile Vision 	com.google.android.gms:play-services-vision:8.4.0
Google Nearby 	com.google.android.gms:play-services-nearby:8.4.0
Google Panorama Viewer 	com.google.android.gms:play-services-panorama:8.4.0
Google Play Game services 	com.google.android.gms:play-services-games:8.4.0
SafetyNet 	com.google.android.gms:play-services-safetynet:8.4.0
Google Wallet 	com.google.android.gms:play-services-wallet:8.4.0
Android Wear 	com.google.android.gms:play-services-wearable:8.4.0

=====================================================================================================================
Abrir leitor de codigo de narras
final Button btScanner = (Button)v.findViewById(R.id.buttonLoteScan);
        btScanner.setOnClickListener(new View.OnClickListener() {
            public void onClick(View v) {
                Intent intent = new Intent("com.google.zxing.client.android.SCAN");
                intent.putExtra("SCAN_FORMATS", "EAN_13,EAN_14,EAN_8,CODE_39,CODE_93,CODE_128,DATA_MATRIX,ITF,CODABAR,QR_CODE_MODE");
                startActivityForResult(intent, 0);
            }
        });

=====================================================================================================================
Bluetooth para desck top
BlueCove library bluecove
sudo apt-get install libbluetooth-dev 
http://snapshot.bluecove.org/distribution/download/2.1.1-SNAPSHOT/

----------------------------------------------------------------------------------------

Gerar Gradlew
Abrir um terminal no seu computador, navegar até a pasta do projeto e digitar.
./gradlew install
http://ricardolecheta.com.br/?p=371
----------------------------------------------------------------------------------------

Compartilhar arquivo txt via bluetooth no android

public void onShareClick(View v) {
    Resources resources = getResources();

    Intent emailIntent = new Intent();
    emailIntent.setAction(Intent.ACTION_SEND);
    // Native email client doesn't currently support HTML, but it doesn't hurt to try in case they fix it
    emailIntent.putExtra(Intent.EXTRA_TEXT, Html.fromHtml(resources.getString(R.string.share_email_native)));
    emailIntent.putExtra(Intent.EXTRA_SUBJECT, resources.getString(R.string.share_email_subject));
    emailIntent.setType("message/rfc822");

    PackageManager pm = getPackageManager();
    Intent sendIntent = new Intent(Intent.ACTION_SEND);     
    sendIntent.setType("text/plain");


    Intent openInChooser = Intent.createChooser(emailIntent, resources.getString(R.string.share_chooser_text));

    List<ResolveInfo> resInfo = pm.queryIntentActivities(sendIntent, 0);

    List<LabeledIntent> intentList = new ArrayList<LabeledIntent>();        

    for (int i = 0; i < resInfo.size(); i++) {
        // Extract the label, append it, and repackage it in a LabeledIntent
        ResolveInfo ri = resInfo.get(i);
        String packageName = ri.activityInfo.packageName;
        if(packageName.contains("android.email")) {
            emailIntent.setPackage(packageName);

        } else if(packageName.contains("twitter") || packageName.contains("facebook") || packageName.contains("mms") || packageName.contains("android.gm")) {
            Intent intent = new Intent();
            intent.setComponent(new ComponentName(packageName, ri.activityInfo.name));
            intent.setAction(Intent.ACTION_SEND);
            intent.setType("text/plain");

            if(packageName.contains("twitter")) {
                intent.putExtra(Intent.EXTRA_TEXT, resources.getString(R.string.share_twitter));

            } else if(packageName.contains("facebook")) {
                // Warning: Facebook IGNORES our text. They say "These fields are intended for users to express themselves. Pre-filling these fields erodes the authenticity of the user voice."
                // One workaround is to use the Facebook SDK to post, but that doesn't allow the user to choose how they want to share. We can also make a custom landing page, and the link
                // will show the <meta content ="..."> text from that page with our link in Facebook.
                intent.putExtra(Intent.EXTRA_TEXT, resources.getString(R.string.share_facebook));

            } else if(packageName.contains("mms")) {
                intent.putExtra(Intent.EXTRA_TEXT, resources.getString(R.string.share_sms));

            } else if(packageName.contains("android.gm")) { // If Gmail shows up twice, try removing this else-if clause and the reference to "android.gm" above
                intent.putExtra(Intent.EXTRA_TEXT, Html.fromHtml(resources.getString(R.string.share_email_gmail)));
                intent.putExtra(Intent.EXTRA_SUBJECT, resources.getString(R.string.share_email_subject));               
                intent.setType("message/rfc822");

            }

            intentList.add(new LabeledIntent(intent, packageName, ri.loadLabel(pm), ri.icon));
        }
    }

    // convert intentList to array
    LabeledIntent[] extraIntents = intentList.toArray( new LabeledIntent[ intentList.size() ]);

    openInChooser.putExtra(Intent.EXTRA_INITIAL_INTENTS, extraIntents);
    startActivity(openInChooser);       
}



==================================================================================================

Exemplos de código
https://www.eecis.udel.edu/~xiwang/java.html

==================================================================================================

Executar Mongo DB
mongod --dbpath /home/anubs/MDWNoSQL
/home/raydacosta/Downloads/data/db	

mongod --dbpath /home/ccrr/mongodb/db --logpath /home/ccrr/mongodb/log

mongod --dbpath /mnt/disks/disk-anubs/mongodb/db --logpath /mnt/disks/disk-anubs/mongodb/log/mongo.log

------------------------------------------------------------------------------------
Iniciar o Mongo automático no win
1 - Entrar no prompt do DOS como ADM
digitar: mongod -dbpath=C:\data\db -logpath=C:\data\db\log.txt -install
Digitar no Executar do win: services.msc

acessar console: mongo

mongod -dbpath=C:\data\db 

---------------------------------------------------------------------------------------------------
Fazer replica de Mongodb
---------------------------------------------------------------------------------------------------
https://mongodbwise.wordpress.com/2014/05/22/mongodb-guia-rapido/


mongod --port 40000 --dbpath '/mnt/disks/disk-anubs/mongodb/arbiter' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/long.0'
mongod --port 40001 --dbpath '/mnt/disks/disk-anubs/mongodb/node1' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/long.1'
mongod --port 40002 --dbpath '/mnt/disks/disk-anubs/mongodb/node2' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/long.2'
mongod --port 40003 --dbpath '/mnt/disks/disk-anubs/mongodb/node3' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/long.3'
mongod --port 40004 --dbpath '/mnt/disks/disk-anubs/mongodb/node4' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/long.4'
mongo

sudo mongod --bind_ip 0.0.0.0 --port 40001 --dbpath '/mnt/disks/disk-anubs/mongodb/node1' --logpath '/mnt/disks/disk-anubs/mongodb/log/log40001.log'
[1] 2375


sudo mongod --bind_ip 0.0.0.0 --port 40001 --dbpath /mnt/disks/disk-anubs/mongodb/node1 --logpath /mnt/disks/disk-anubs/mongodb/log/log40001.log&


mongod --bind_ip 0.0.0.0 --port 40000 --dbpath '/mnt/disks/disk-anubs/mongodb/arbiter' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.0'&
mongod --bind_ip 0.0.0.0 --port 40001 --dbpath '/mnt/disks/disk-anubs/mongodb/node1' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.1'&
mongod --bind_ip 0.0.0.0 --port 40002 --dbpath '/mnt/disks/disk-anubs/mongodb/node2' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.2'&
mongod --bind_ip 0.0.0.0 --port 40003 --dbpath '/mnt/disks/disk-anubs/mongodb/node3' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.3'&
mongod --bind_ip 0.0.0.0 --port 40004 --dbpath '/mnt/disks/disk-anubs/mongodb/node4' --replSet MDW --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.4'&


mongod --bind_ip 0.0.0.0 --port 40000 --dbpath '/mnt/disks/disk-anubs/mongodb/arbiter' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.0'&
mongod --bind_ip 0.0.0.0 --port 40001 --dbpath '/mnt/disks/disk-anubs/mongodb/node1' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.1'&
mongod --bind_ip 0.0.0.0 --port 40002 --dbpath '/mnt/disks/disk-anubs/mongodb/node2' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.2'&
mongod --bind_ip 0.0.0.0 --port 40003 --dbpath '/mnt/disks/disk-anubs/mongodb/node3' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.3'&
mongod --bind_ip 0.0.0.0 --port 40004 --dbpath '/mnt/disks/disk-anubs/mongodb/node4' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.4'&


rm /mnt/disks/disk-anubs/mongodb/arbiter/* -R
rm /mnt/disks/disk-anubs/mongodb/node1/* -R
rm /mnt/disks/disk-anubs/mongodb/node2/* -R
rm /mnt/disks/disk-anubs/mongodb/node3/* -R
rm /mnt/disks/disk-anubs/mongodb/node4/* -R
rm /mnt/disks/disk-anubs/mongodb/log/* -R
rm /mnt/disks/disk-anubs/mongodb/db/* -R



mongod --bind_ip 0.0.0.0 --port 40000 --dbpath '/mnt/disks/disk-anubs/mongodb/arbiter' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.0'&
mongod --bind_ip 0.0.0.0 --port 40001 --dbpath '/mnt/disks/disk-anubs/mongodb/node1' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.1'&
mongod --bind_ip 0.0.0.0 --port 40002 --dbpath '/mnt/disks/disk-anubs/mongodb/node2' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.2'&
mongod --bind_ip 0.0.0.0 --port 40003 --dbpath '/mnt/disks/disk-anubs/mongodb/node3' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.3'&
mongod --bind_ip 0.0.0.0 --port 40004 --dbpath '/mnt/disks/disk-anubs/mongodb/node4' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/mnt/disks/disk-anubs/mongodb/log/log.4'&


mongod --bind_ip 0.0.0.0 --port 40001 --dbpath '/mnt/disks/disk-anubs/mongodb/node1' --logpath '/mnt/disks/disk-anubs/mongodb/log/log.1'&


//Importar dados no mongo
mongoimport --db MDWCloud -c ItemSerial --drop --file /home/raydacosta/Downloads/ItemSerial/ItemSerial.json




rs.add( { host: "10.158.0.4:40001", priority: 0, votes: 0 } )
rs.add( { host: "10.158.0.4:40002", priority: 10, votes: 0 } )
rs.add( { host: "10.158.0.4:40003", priority: 20, votes: 0 } )
rs.add( { host: "10.158.0.4:40004", priority: 30, votes: 0 } )


// MARCAR AS MAQUIUNAS PARA PRIMARIA
var config= {_id: 'MDWCloud',  members: [{ _id: 0, host: '10.158.0.4:40000', arbiterOnly: true },{ _id:1,host:'10.158.0.4:40001',priority:2 },{ _id:2, host: '10.158.0.4:40002',priority:1 },{ _id: 3, host: '10.158.0.4:40003',priority:1 },{ _id: 4, host: '10.158.0.4:40004',priority:1 }]};
rs.initiate(config)
rs.conf(config);
rs.conf();


//OUTRA FORMA
cfg = rs.conf(); cfg.members[1].priority = 2; rs.reconfig(cfg);



mongo "mongodb://10.158.0.4:40000,10.158.0.4:40001,10.158.0.4:40002,10.158.0.4:40003,10.158.0.4:40004/?replicaSet=MDWCloud"

show collections;
use MDWCloud



tail -f /mnt/disks/disk-anubs/mongodb/log/long.0
tail -f /mnt/disks/disk-anubs/mongodb/log/long.1
tail -f /mnt/disks/disk-anubs/mongodb/log/long.2
tail -f /mnt/disks/disk-anubs/mongodb/log/long.3
tail -f /mnt/disks/disk-anubs/mongodb/log/long.4





mongod --port 40000 --dbpath '/home/raydacosta/arbiter' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/home/raydacosta/arbiter/long.1'
mongod --port 40001 --dbpath '/home/raydacosta/node1' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/home/raydacosta/arbiter/long.2'
mongod --port 40002 --dbpath '/home/raydacosta/node1' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/home/raydacosta/arbiter/long.3'
mongod --port 40003 --dbpath '/home/raydacosta/node1' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/home/raydacosta/arbiter/long.3'
mongod --port 40004 --dbpath '/home/raydacosta/node1' --replSet MDWCloud --smallfiles --oplogSize 128 --logpath '/home/raydacosta/arbiter/long.3'
mongo

MongoClient mongoClient = new MongoClient(Arrays.asList( new ServerAddress("10.158.0.4", 40000), 
                                                                          new ServerAddress("10.158.0.4", 40001), 
                                                                          new ServerAddress("10.158.0.4", 40002), 
                                                                          new ServerAddress("10.158.0.4", 40003), 
                                                                          new ServerAddress("10.158.0.4", 40004)), options); 


mongod --port 41000 --dbpath "C:\data\arbiter" --replSet MDWCloud --smallfiles --oplogSize 128 --logpath "C:\data\log\long.0"
mongod --port 40001 --dbpath "C:\data\node1" --replSet MDWCloud --smallfiles --oplogSize 128 --logpath "C:\data\log\long.1"
mongod --port 40002 --dbpath "C:\data\node2" --replSet MDWCloud --smallfiles --oplogSize 128 --logpath "C:\data\log\long.2"
mongod --port 40003 --dbpath "C:\data\node3" --replSet MDWCloud --smallfiles --oplogSize 128 --logpath "C:\data\log\long.3"
mongod --port 40004 --dbpath "C:\data\node4" --replSet MDWCloud --smallfiles --oplogSize 128 --logpath "C:\data\log\long.4"
mongo --port 40001  
mongo --port 27017 --dbpath '/home/raydacosta/data/db'

rs.initiate()
rs.conf()
rs.status()
db.isMaster()// verifica se é master
rs.reconfig({ force: true })

// tortar prioridade o mandatorio replica
cfg = rs.conf();
cfg.members[1].priority = 2;
rs.reconfig(cfg);

ADM
mongodump
mongorestore
mongostat
mongotop - mongotop 30



rs.addArb(localhost:30000)
rs.slaveOk()
ps auxww | grep mongo


-- var config= {_id: 'MDWCloud',  members: [{ _id: 0, host: '127.0.0.1:41000', arbiterOnly: true },{ _id: 1, host: '127.0.0.1:40001' },{ _id: 2, host: '127.0.0.1:40002' },{ _id: 3, host: '127.0.0.1:40003' },{ _id: 4, host: '127.0.0.1:40004' }]};
-- var config= {_id: 'MDWCloud',  members: [{ _id: 5, host: '127.0.0.1:41000', arbiterOnly: true },{ _id: 1, host: '127.0.0.1:40001' },{ _id: 2, host: '127.0.0.1:40002' },{ _id: 3, host: '127.0.0.1:40003' },{ _id: 4, host: '127.0.0.1:40004' }]};
var config= {_id: 'MDWCloud',  members: [{ _id: 0, host: '0.0.0.0:40000', arbiterOnly: true },{ _id:1,host:'127.0.0.1:40001' },{ _id:2, host: '127.0.0.1:40002' },{ _id: 3, host: '127.0.0.1:40003' },{ _id: 4, host: '127.0.0.1:40004' }]};
rs.initiate(config)
rs.conf(config);
rs.conf();

mongo "mongodb://127.0.0.1:41000,127.0.0.1:40001,127.0.0.1:40002,127.0.0.1:40003, 127.0.0.1:40004/?replicaSet=MDWCloud"


MONGODB
Exemplo
Inicie o seu servidor mongod. 
Supondo-se que o servidor mongod está sendo executado no 
localhost e na porta 27017. 
Agora, abra um prompt de comando e vá para o diretório bin da sua 
instância MongoDB e digite o comando mongodump

mongodump

mongorestore

show dbs;

use MDWCloud;
show collections;

db.Item.find();

db.Item.find().pretty()

db.Item.find({"Process": {$all: "SERIALIZAÇÃO"}).pretty()

db.Item.find({"Process":{$gte:"SERIALIZAÇÃO"}}, {char: 1});

db.Item.find({epc: {$gte: 105}})

db.Item.find({epc: {$gte: 105}}).count();

db.Item.find({"epc":{$all:["3075E1A685E60C40000003FB"]}}).pretty();

db.Item.find({epc:{$in:[3075E1A6856B61C000000073]}}, {char: 1});

db.Item.find({"epc":{$gte:"3035E1A2700063000000021F"}}, {char: 1});


db.ItemDB.find({"IdObjeto":{$gte:"1479472534815"}}).pretty();

db.ItemDB.find({"IdObjeto":{$all:"1479472534815"}}).pretty();

db.Item.find({"Process":{$in:["SERIALIZAÇÃO"]}});


db.ItemDB.find({"Epc":{$all:"3035E1A270007840000001CA"}}).pretty();

db.Item.find({"DataCriado":{$lt:ISODate("2019-01-20")}).pretty();

db.Item.find({ DataCriado: { $gt: ISODate('2017-01-01') } });




db.Item.find({ DataCriado: { $gt: ISODate("2019-01-23T01:00:00Z")} });
db.Item.find({ "DataCriado": { $gte: ISODate("2019-01-23T01:00:00Z")} });
db.Item.find({ "DataCriado": { $gte: ISODate("2019-01-23T01:00:00Z")} }).count();
db.Item.find({IdEmpresa: "0123456777", "DataCriado": { $gt: ISODate("2019-01-23T01:00:00Z")} });
db.Item.find({IdEmpresa: "0123456777", "DataCriado": { $gt: ISODate("2019-01-23T01:00:00Z")} }).count();
db.Item.find({IdEmpresa: "0123456789", "DataCriado": { $gte: ISODate("2019-02-01T01:00:00Z")} }).count();
1322901037








db.ItemDB.find({"IdObjeto":{$all:["1479472534815"]}}).pretty();
db.ItemDB.find({"IdObjeto":{$all:["1479472534815"]}}).pretty();
db.Item.find({"IdObjeto":{$in:["1479472534815"]}});
db.Item.find({"Id":{$in:["0"]}});
db.Item.find({"epc":{$all:["3075E1A6856B61C000000073"]}});


db.Item.update({"IdObjeto":"110cb0f4-0033-4ee6-9584-801af72fa954"}, {$set:{Status:"Coletado"}});


db.Item.find({"IdObjeto":"110cb0f4-0033-4ee6-9584-801af72fa954"}).pretty();
db.Item.find({"DataCriado" : ISODate("2019-01-24T19:09:02.071Z")}).pretty();
db.Item.find({"DataCriado" : {$lte: ISODate("2019-12-01T19:09:02.071Z")}}).pretty();

db.Item.find({"DataCriado" : {$lte: ISODate("2019-12-01T19:09:02.071Z")}}).count();


db.Item.update({"DataCriado" : {$gte: ISODate("2018-12-01T19:09:02.071Z")}}, {$set:{SYNCRONIZADOR:"0"}});
db.Item.update({DataCriado : {$gt: ISODate("2018-12-01T19:09:02.071Z")}}, {$set:{SYNCRONIZADOR:"0"}});
db.Item.update({DataCriado : {$gte: ISODate("2018-12-01")}}, {$set:{SYNCRONIZADOR:"0"}});
db.Item.update({DataCriado : {$gte: ISODate("2018-12-01")}}, {$set:{SYNCRONIZADOR:0}},{ multi: true });

db.Item.update({DataCriado : {$gte: ISODate("2019-01-28")}}, {$set:{SYNCRONIZADOR:0}},{ multi: true });
db.ItemSerial.update({DataCriado : {$gte: ISODate("2019-01-01")}}, {$set:{SYNCRONIZADOR:0}},{ multi: true });
db.Item.update({DataCriado : {$gte: ISODate("2018-01-28")}}, {$set:{SYNCRONIZADOR:1}},{ multi: true });
db.Item.find({"Epc":"3035E1B08430EAC000000001"}).pretty();

WFLYSRV0236


    $lt (menor que)
    $lte (menor ou igual a)
    $gt (maior que)
    $gte (maior ou igual a)
    $all (corresponder a todos os valores em um array)
    $exists (verificar se um campo existe ou não)
    $mod (módulo)
    $ne (não igual)
    $in (corresponder a um ou mais valores em um array)
    $nin (corresponder a valores zero em um array)
    $or (corresponder uma consulta a outra)
    $nor (não corresponder uma consulta nem outra)
    $size (corresponder qualquer array com número definido de elementos)
    $type (corresponder valores com tipo de dados BSON especificado)
    $not (não igual a)




Equality 	{<key>:<value>} 	db.mycol.find({“by”:”tutorials point”}).pretty() 	where by = ‘tutorials point’
Less Than 	{<key>:{$lt:<value>}} 	db.mycol.find({“likes”:{$lt:50}}).pretty() 	where likes < 50
Less Than Equals 	{<key>:{$lte:<value>}} 	db.mycol.find({“likes”:{$lte:50}}).pretty() 	where likes <= 50
Greater Than 	{<key>:{$gt:<value>}} 	db.mycol.find({“likes”:{$gt:50}}).pretty() 	where likes > 50
Greater Than Equals 	{<key>:{$gte:<value>}} 	db.mycol.find({“likes”:{$gte:50}}).pretty() 	where likes >= 50
Not Equals 	{<key>:{$ne:<value>}} 	db.mycol.find({“likes”:{$ne:50}}).pretty() 	where likes != 50


==================================================================================================
Instalar MongoDB no Ubuntu

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo apt-get install -y mongodb-org=3.6.5 mongodb-org-server=3.6.5 mongodb-org-shell=3.6.5 mongodb-org-mongos=3.6.5 mongodb-org-tools=3.6.5
echo "mongodb-org hold" | sudo dpkg --set-selections
echo "mongodb-org-server hold" | sudo dpkg --set-selections
echo "mongodb-org-shell hold" | sudo dpkg --set-selections
echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
echo "mongodb-org-tools hold" | sudo dpkg --set-selections


sudo service mongod start

[initandlisten] waiting for connections on port 27017

sudo service mongod stop



//retornar as SKU que estão cadastradas sem repetir o registro, para isso basta colocar o distinct.
db.getCollection('ItemSerial').distinct("Sku")


//Like
db.getCollection('ItemSerial').find({"Sku":/Ba/});



//Ordenando dados.
db.getCollection('ItemSerial').find({},{"sigla":1,"Sku":1}).sort({"Sku":1})
db.getCollection('ItemSerial').find({},{"sigla":1,"Sku":1}).sort({"Sku":-1})



// identificar duplicidade
db.ItemSerial.aggregate([
  { $group: {
    _id: { Sku: "$name" },   // replace `name` here twice
    duplicados: { $addToSet: "$_id" },
    count: { $sum: 1 } 
  } }, 
  { $match: { 
    count: { $gte: 2 } 
  } },
  { $sort : { count : -1} },
  { $limit : 10 }
]);





db.ItemSerial.aggregate([{ $group: {_id: { Sku: "$name" }, duplicados: { $addToSet: "$_id" }, count: { $sum: 1 }  } }, { $match: {  count: { $gte: 2 }  } }, { $sort : { count : -1} }, { $limit : 10 }]);
db.ItemSerial.aggregate([{ $group: {_id: { Sku: "$name" }, duplicados: { $addToSet: "$_id" }, count: { $sum: 1 }  } }, { $match: {  count: { $gte: 2 }  } }, { $sort : { count : -1} }, { $limit : 10 }]).pretty();



db.test.find()                                              
{ "_id" : ObjectId("4ecc05e55dd98a436ddcc47c"), "x" : 1 }      

db.ItemSerial.find({"_id": ObjectId("5c49ed71d93af444078c4441")}).pretty();

db.ItemSerial.find({"Sku": "1250755005"}).pretty();



==================================================================================================












vmstat e iostat
A ferramenta vmstat fornece um relatório com informações relevantes sobre os processos, memória, paginação (swap), I/O e CPU. 
Sua interatividade é limitada, no entanto, é uma excelente 

mytop
Como o próprio nome sugere, o mytop é um clone do comando top para o MySQL. Sua interface exibe, ao invés de processos, as threads (queries em execução, por exemplo) e informações gerais sobre o servidor MySQL. Essas informações incluem o total de queries, média de queries por segundo, bytes enviados e recebidos, e o número de queries lentas, que são aquelas cujo tempo de processamento ultrapassa, por padrão, 10 segundos.


===================================================================================================

mysql -uroot -p

use mdwcloud3

source   caminho/do/arquivo/nome_arquivo.sql;

check table MDWCloud_ItemEntity

repair table MDWCloud_ItemEntity
select concat('repair table ', table_name, ';') from information_schema.tables

show processlist
show table status;

show variables where variable_name = 'max_connections';

select * 
3075E1A68458E1C00000151B


==ver espaco de tabela
SELECT TABLE_SCHEMA, 
TABLE_NAME, CONCAT(ROUND(data_length / ( 1024 * 1024 ), 2), 'MB') DATA, 
            CONCAT(ROUND(data_free  / ( 1024 * 1024 ), 2), 'MB')FREE 
from information_schema.TABLES where TABLE_SCHEMA NOT IN ('information_schema','mysql') 
and Data_free < 0;


=======================================================================================================
sudo mysql -u root
mysql> USE mysql;
mysql> CREATE USER 'root'@'localhost' IDENTIFIED BY '';
mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost';
mysql> UPDATE user SET plugin='auth_socket' WHERE User='root';
mysql> FLUSH PRIVILEGES;
mysql> exit;

$ service mysql restart



=======================================================================================================

select id,item_dataCriado from `mdwcloud3`.`MDWCloud_ItemEntity`  where item_epc = '3075E1A68458E1C000001519';   
UPDATE `mdwcloud3`.`MDWCloud_ItemEntity` SET `item_romaneioitem_id`= null  WHERE item_romaneioitem_id = 0  and id = 339451;



=======================================================================================================

sudo rm /var/lib/apt/lists/* ; 
sudo rm /var/lib/apt/lists/partial/* ; 
sudo apt-get clean ; 
sudo apt-get -f install ; 
sudo apt-get update



=======================================================================================================

ssh-rsa SHA256:CTxBAg9g8KUfLhNDMQAcCOnDw4UxM+OqM+hkiK8IBgM raydacosta


=======================================================================================================
ACESSAR WILDFLY VIA JCONSOLE
jconsole -J-Djava.class.path="/usr/lib/jvm/java-8-oracle/lib/tools.jar:/usr/lib/jvm/java-8-oracle/lib/jconsole.jar:/home/raydacosta/wildfly/bin/client/jboss-cli-client.jar"
service:jmx:http-remoting-jmx://127.0.0.1:9990
service:jmx:http-remoting-jmx://35.199.125.177:9888

service:jmx:remote+http://35.199.125.177:9888
admin
sucesso123

service:jmx:rmi://35.199.125.177:9888/jmxrmi


service:jmx:rmi:///jndi/rmi://35.199.125.177:9888/jmxrmi



Validar porta
netstat -a | grep 9888


Jvisualvm
/usr/lib/jvm/java-8-oracle/bin/jvisualvm


rmiregistry 9889&jstatd -J-Djava.security.policy=all.policy -p 9889


jstatd -J-Djava.security.policy=/home/ccrr/jstatd.all.policy -J-Djava.rmi.server.hostname=35.199.125.177 -J-Djava.net.preferIPv4Stack=true -J-Djava.rmi.server.logCalls=true


./visualvm -Dcom.sun.management.jmxremote=true -Dcom.sun.management.jmxremote.ssl=false -Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.port=9888 -Dcom.sun.management.jmxremote.rmi.port=1098 -Djava.rmi.server.hostname=35.199.125.177

java -Dcom.sun.management.jmxremote.port=3333 \ -Dcom.sun.management.jmxremote.ssl=false \ -Dcom.sun.management.jmxremote.authenticate=false \ visualvm 


/usr/lib/jvm/java-8-oracle/jre/lib/management/jmxremote.password.template
service:jmx:rmi:///jndi/rmi://35.199.125.177:9888/jmxrmi

monitorRoleUser  pass1
controlRoleUser  pass2



jvisualvm --cp:a /usr/lib/jvm/java-8-oracle/lib/jboss-cli-client.jar


service:jmx:remoting-jmx://35.199.125.177:9888


-Dcom.sun.management.jmxremote.port=9999 \-Dcom.sun.management.jmxremote.authenticate=false \ -Dcom.sun.management.jmxremote.ssl=false \
=======================================================================================================

Altear a senha de SVN
sudo nano /etc/subversion/passwd
htpasswd /etc/subversion/passwd lucas



=======================================================================================================
ACESSAR JBOSS VIA MANAGER

http://35.199.125.177:9888/management?operation=attribute&name=server-state&json.pretty=1
http://35.199.125.177:9888/management/subsystem/undertow/server/default-server?operation=resource&recursive=true&json.pretty=1


=======================================================================================================
React Native por onde começar, obrigado Diego Oliveira pela colaboração:

# Comece aqui

Getting Started
https://facebook.github.io/react-nat…/…/getting-started.html

Learn The Basics
https://facebook.github.io/react-native/docs/tutorial.html

React Native Overview
https://www.tutorialspoint.com/re…/react_native_overview.htm

# Udemy (melhores cursos, mas pago)

Build Apps with React-Native
https://www.udemy.com/reactnative/learn/v4/overview

The Complete React Native and Redux Course
https://www.udemy.com/the-complete-react-native-…/…/overview

# Util

Component Lifecycle
https://reactjs.org/docs/react-component.html

Carbon UI - Material Design Components for React Native
https://carbon-ui.com/

Getting Started with React Native and Redux (IMPORTANTE)
https://medium.com/…/getting-started-with-react-native-redu…

=======================================================================================================

// instalar o ionic+cordova
sudo npm install -g ionic cordova

//executar o server
ionic serve -l

//url
http://localhost:8200/

// json de steste
https://api.tvmaze.com/singlesearch/shows?q=the-walking-dead&embed=episodes
https://restcountries.eu/rest/v2/all

// cria servico rest
sudo ionic generate service RestApi


// instalar cordova
sudo npm install -g cordova

//instalar adroid para  cordova
sudo ionic cordova platform add android

//executar no android
sudo ionic cordova run android


//buildar no android
sudo ionic cordova run android



-------------------------------------------

//Android Studio project detected
//ANDROID_HOME=/usr/lib/android-sdk
//JAVA_HOME=/usr/lib/jvm/java-8-oracle
set GRADLE_HOME=/home/raydacosta/android-studio/gradle/gradle-4.6
//ng run app:ionic-cordova-build --platform=android



// desinstalar 
sudo npm uninstall -g cordova
sudo npm install -g cordova
sudo ionic cordova platform rm android


~\AppData\Local\Android\sdk\tools\bin
sudo android list sdk --all
sudo android update sdk -u -a -t "android-19"
sudo sdkmanager "platform-tools" "platforms;android-19"
sudo sdkmanager "build-tools;19"

sudo /home/raydacosta/Android/Sdk/tools/bin/sdkmanager "platform-tools" "platforms;android-19"
sudo /home/raydacosta/Android/Sdk/tools/bin/sdkmanager "build-tools;19.1.0"

sudo update sdk -u -a -t 19 android update sdk -u -a -t 20


//-----------------------------------------
//     criar uma aplicação em branco
//-----------------------------------------
sudo ionic start oimundo blank
sudo npm i
sudo chmod 777 /home/raydacosta/ProjetoAngular -R
sudo npm i --save -E @ionic/pro
sudo npm i -D -E @ionic/lab
sudo npm install -g ionic cordova
sudo ionic cordova platform add android
sudo ionic generate service authService
sudo ionic generate page register
sudo ionic generate page login
sudo npm install -g cordova
sudo ionic cordova platform add android
sudo cordova run android --device
sudo ionic cordova run android --device
sudo ionic serve -l


ionic run android --device
//-----------------------------------------
//     criar uma aplicação em branco
//-----------------------------------------
sudo ionic start oi-mundo blank
sudo npm i
sudo chmod 777 /home/raydacosta/ProjetoAngular -R
sudo npm i --save -E @ionic/pro
sudo npm i -D -E @ionic/lab
sudo npm install -g ionic cordova
sudo ionic cordova platform add android
sudo npm install -g cordova
sudo ionic cordova platform add android
sudo cordova run android
sudo ionic cordova run android --verbose 
sudo ionic serve -l



export JAVA_HOME="/usr/lib/jvm/java-8-oracle" \
&& export PATH=$JAVA_HOME/bin:$PATH \
&& export ANDROID_HOME=$HOME/Android/Sdk \
&& export PATH=${PATH}:${ANDROID_HOME}/tools \
&& export PATH=${PATH}:${ANDROID_HOME}/platform-tools \
&& export GRADLE_HOME=/home/raydacosta/android-studio/gradle/gradle-4.6 \
export PATH=$PATH:$GRADLE_HOME/bin


//=======================================================================
kafka

./zookeeper-server-start.sh config/zookeeper.properties
./kafka-server-start.sh config/server.properties
./kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic mdwrecebimento


//=======================================================================


sudo snap install mosquitto          # version 1.5.5, or
sudo apt  install mosquitto-clients





//=======================================================================
Problema: mysql Too many connections - Solucao
show processlist;
show variables like '%max_connections%';
set global max_connections = 9000;

max_connections=300
max_user_connections=280


//=======================================================================

setar java no Java_home no linux
siudo nano /etc/environment
JAVA_HOME="/usr/lib/jvm/java-8-oracle/jre/bin/java"
source /etc/environment
echo $JAVA_HOME

sudo add-apt-repository ppa:webupd8team/java
sudo apt update
sudo apt install oracle-java8-installer
sudo apt install oracle-java8-set-default
