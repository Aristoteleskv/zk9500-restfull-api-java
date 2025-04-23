# zk9500-restfull-api-java

API Rest para dispositivo leitor de impressão digital ZK9500
Antes de executar esta API Rest, você precisa instalar algumas das ferramentas em sua máquina local
Z9500 SDK PARA WINDOWS
JAVA SDK
Apache Maven
Se você estiver usando o VSCode, recomendo que instale

Pacote de extensão para Java
Depois de instalar todas as ferramentas acima, execute o código a seguir no terminal no diretório principal, para instalar todas as dependências

 $ mvn clean package
Depois de executar o comando acima no terminal, execute o seguinte comando no terminal no diretório principal, para executar a API REST

 $  mvn exec:java -Dexec.mainClass="com.zk.App"
Para a instalação gerada no Windows

 $  jpackage --input target/ --name ZK9500-rest-api --main-jar ZK9500-REST-API.jar --main-class com.zk.App --type msi/exe --dest target/msi -UI
$  jpackage  --input target/  --name ZK9500-rest-api --main-jar ZK9500-REST-API.jar --main-class com.zk.App --type exe  --dest target/exe --win-console Without UI
Dependências usadas
   <dependencies>
       <dependency>
       <groupId>junit</groupId>
       <artifactId>junit</artifactId>
       <version>3.8.1</version>
       <scope>test</scope>
       </dependency>
       <dependency>
       <groupId>org.glassfish.jersey.containers</groupId>
       <artifactId>jersey-container-grizzly2-http</artifactId>
       <version>2.35</version>
       </dependency>
       <dependency>
       <groupId>org.glassfish.jersey.core</groupId>
       <artifactId>jersey-server</artifactId>
       <version>2.35</version>
       </dependency>
       <dependency>
       <groupId>org.glassfish.jersey.inject</groupId>
       <artifactId>jersey-hk2</artifactId>
       <version>2.35</version>
       </dependency>
       <dependency>
       <groupId>org.glassfish.jersey.containers</groupId>
       <artifactId>jersey-container-servlet-core</artifactId>
       <version>2.35</version>
       </dependency>
       <dependency>
       <groupId>com.zk</groupId>
       <artifactId>ZKFingerReader</artifactId>
       <version>1.0.0</version>
       </dependency>
       <dependency>
       <groupId>io.socket</groupId>
       <artifactId>socket.io-client</artifactId>
       <version>2.1.1</version>
       </dependency>
       <dependency>
       <groupId>com.corundumstudio.socketio</groupId>
       <artifactId>netty-socketio</artifactId>
       <version>1.7.22</version>
       </dependency>
       <dependency>
       <groupId>io.netty</groupId>
       <artifactId>netty-all</artifactId>
       <version>4.1.79.Final</version>
       </dependency>
       <dependency>
       <groupId>com.google.code.gson</groupId>
       <artifactId>gson</artifactId>
       <version>2.8.7</version>
       </dependency>
       <dependency>
       <groupId>org.glassfish.jersey.media</groupId>
       <artifactId>jersey-media-json-jackson</artifactId>
       <version>2.35</version>
       </dependency>
       <dependency>
       <groupId>com.fasterxml.jackson.core</groupId>
       <artifactId>jackson-databind</artifactId>
       <version>2.12.5</version>
       </dependency>
       <dependency>
       <groupId>org.glassfish.jersey.media</groupId>
       <artifactId>jersey-media-json-processing</artifactId>
       <version>2.42</version>
       </dependency>
   </dependencies>
Pontos de extremidade para API
POST http://localhost:8080/fingerprint/open -> Para abrir/girar o dispositivo

POST http://localhost:8080/fingerprint/enroll -> Para inscrever a impressão digital após 3 vezes de digitalização

POST http://localhost:8080/fingerprint/verify-fingerprint -> Para verificar a impressão digital salvada no cache

POST http://localhost:8080/fingerprint/register -> Para registrar a impressão digital após o registro

POST http://localhost:8080/fingerprint/close -> Para fechar/desligar o dispositivo
