<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.git.test</groupId>
    <artifactId>git-maven</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
        <java.version>1.8</java.version>
        <distributionManagement.directory.name>my_test</distributionManagement.directory.name>
        <github.global.server>github</github.global.server>
    </properties>

    <distributionManagement>
        <repository>
            <id>my_test</id>
            <name>hlj managemaent name</name>
            <url>file://${project.build.directory}/${distributionManagement.directory.name}</url>
        </repository>
    </distributionManagement>
    <build>
        <plugins>
            <!--maven发布插件-->
            <plugin>
                <artifactId>maven-deploy-plugin</artifactId>
                <version>2.8.1</version>
                <configuration>
                    <altDeploymentRepository>internal.repo::default::file://${project.build.directory}/${distributionManagement.directory.name}/mvn-repo</altDeploymentRepository>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
