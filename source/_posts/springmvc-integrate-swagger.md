title: springmvc integrate swagger
date: 2016-05-26 16:24:03
tags:
---
title: springmvc integrate swagger
tags:
---

参考链接
[http://blog.csdn.net/linlzk/article/details/50728264](http://blog.csdn.net/linlzk/article/details/50728264)



集成swagger ui 
```maven
  <plugin>
                        <groupId>com.googlecode.maven-download-plugin</groupId>
                        <artifactId>download-maven-plugin</artifactId>
                        <version>1.2.1</version>
                        <executions>
                          <execution>
                            <id>swagger-ui</id>
                            <phase>prepare-package</phase>
                            <goals>
                                <goal>wget</goal>
                            </goals>
                            <configuration>
                              <url>https://github.com/swagger-api/swagger-ui/archive/v${swagger-ui.version}.tar.gz</url>
                              <unpack>true</unpack>
                              <outputDirectory>${project.build.directory}</outputDirectory>
                            </configuration>
                          </execution>
                        </executions>
                    </plugin>
                    <plugin>
                        <groupId>org.apache.maven.plugins</groupId>
                        <artifactId>maven-war-plugin</artifactId>
                        <version>2.6</version>
                        <configuration>
                            <warName>${project.build.finalName}</warName>
                            <webappDirectory>${basedir}/target/${project.build.finalName}</webappDirectory>
                            <webResources>
                                <webResource>
                                    <directory>${project.build.directory}/swagger-ui-${swagger-ui.version}/dist</directory>
                                    <targetPath>swagger-ui</targetPath>
                                </webResource>
                            </webResources>
                        </configuration>
                    </plugin>
```

