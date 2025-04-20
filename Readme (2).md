  378  java -version
  379  mvn -version
  380  mkdir hello-java-maven
  381  cd hello-java-maven
  382  mkdir -p src/main/java
  383  touch pom.xml
  384  touch src/main/java/HelloWorld.java
  385  cat > src/main/java/HelloWorld.java <<EOF
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
EOF

  386  cat > pom.xml <<EOF
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
         http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>hello</artifactId>
    <version>1.0</version>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>

</project>
EOF

  387  mvn clean package
  388  target/hello-1.0.jar
  389  java -cp target/hello-1.0.jar HelloWorld
  390  history
