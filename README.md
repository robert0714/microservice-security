# microservice-security
The first commit contains a demo of how to consume the UAA and Google OpenID Connect as identity providers

The rest of the commits outline how to create, secure, and test the security of microservices, one step at a time.


Video: https://www.youtube.com/watch?v=USMl2GNg2r0

Slide: http://www.slideshare.net/SpringCentral/securing-microservices-with-spring-cloud-security-53170178

In eclipse.ini I got the addition: -javaagent:../Eclipse/lombok.jar

lombok.jar was added to the same directory as eclise.ini /Applications/Eclipse.app/Contents/Eclipse

in pom.xml
http://awhitford.github.io/lombok.maven/lombok-maven-plugin/faq.html
<build>
  <sourceDirectory>target/generated-sources/delombok</sourceDirectory>
  <testSourceDirectory>target/generated-test-sources/delombok</testSourceDirectory>
  <plugin>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok-maven-plugin</artifactId>
    <version>1.16.16.0</version>
    <executions>
      <execution>
        <id>delombok</id>
        <phase>generate-sources</phase>
        <goals>
          <goal>delombok</goal>
        </goals>
        <configuration>
          <addOutputDirectory>false</addOutputDirectory>
          <sourceDirectory>src/main/java</sourceDirectory>
        </configuration>
      </execution>
      <execution>
        <id>test-delombok</id>
        <phase>generate-test-sources</phase>
        <goals>
          <goal>testDelombok</goal>
        </goals>
        <configuration>
          <addOutputDirectory>false</addOutputDirectory>
          <sourceDirectory>src/test/java</sourceDirectory>
        </configuration>
      </execution>
    </executions>
  </plugin>
</build>

<dependencies>
  <dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.16.16</version>
    <scope>provided</scope>
  </dependency>
</dependencies>


lombok 註解：    
lombok 提供的註解不多，可以參考官方視頻的講解和官方文檔。    
Lombok 註解在線幫助文檔：http://projectlombok.org/features/index.     
下面介紹幾個我常用的 lombok 註解：         
@Data   ：註解在類上；提供類所有屬性的 getting 和 setting 方法，此外還提供了equals、canEqual、hashCode、toString 方法         
@Setter：註解在屬性上；為屬性提供 setting 方法         
@Getter：註解在屬性上；為屬性提供 getting 方法         
@Log4j ：註解在類上；為類提供一個屬性名為log 的log4j 日誌對象@NoArgsConstructor：註解在類上；為類提供一個無參的構造方法@AllArgsConstructor：註解在類上；為類提供一個全參的構造方法
