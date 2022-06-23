## Como usar:
O projeto a ser monitorado deve ser um projeto que utiliza a framework do Spring

### Como transformar adicionar a framework do SpringBoot a um projeto existente:
Para adicionar a framework do spring em um projeto maven, basta adicionar no pom.xml os seguintes atributos:

Após a declaração do groupId, artifactId e version:
<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.6.1</version>
		<relativePath />
</parent>

Após a declaração dos dependencies:
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
  </build>
  
Com isso, já adicionamos a framework ao projeto.
Agora caso deseja-se fazer endpoints, adicionamos a dependência:
```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

### Como adicionar o actuator em um projeto Spring:
Para adicionar o actuator a um projeto Spring existente, adicione as seguintes dependências ao pom.xml:
```xml
<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
<dependency>
		<groupId>de.codecentric</groupId>
		<artifactId>spring-boot-admin-starter-client</artifactId>
		<version>2.2.0</version>
</dependency>
```

Após isso, adicione as seguintes configurações no _application.properties_:
> management.endpoints.web.exposure.include=*  
> spring.boot.admin.client.url=http://localhost:8089/  

No management, estamos expondo todos endpoints, ja na url temos que informar a url de onde o SpringBoot-Admin está sendo executado.
