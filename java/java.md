☕ JAVA – comandos essenciais
# Java - Comandos Básicos

## Compilar
javac Main.java

## Executar
java Main

## Versão instalada
java -version
javac -version

## Executar JAR
java -jar app.jar

## Variáveis de ambiente
echo %JAVA_HOME%    # Windows
echo $JAVA_HOME     # Linux/Mac

🧩 MAVEN
mvn.md
# Maven - Comandos principais

## Criar projeto
mvn archetype:generate

## Build
mvn clean install

## Rodar testes
mvn test

## Rodar aplicação Spring Boot
mvn spring-boot:run

## Baixar dependências
mvn dependency:resolve

mvnw.md
# Maven Wrapper (.mvnw)

## Rodar build sem Maven instalado
./mvnw clean install

## Spring Boot
./mvnw spring-boot:run

## Windows
mvnw.cmd clean install