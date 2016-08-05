title: maven tomcat plugin
date: 2016-06-06 17:46:19
tags:
---
title: maven tomcat plugin
tags:
---
```config
<plugin>
				<groupId>org.apache.tomcat.maven</groupId>
				<artifactId>tomcat7-maven-plugin</artifactId>
				<version>2.2</version>

				 <configuration>
				  <!-- Have Tomcat look in the file filtering folder -->
				  <warSourceDirectory>
					${project.build.directory}/${project.artifactId}-${project.version}
				  </warSourceDirectory>
				</configuration>
		   </plugin>
```


```shell
$mvn tomcat7:run
```
reference link
[http://tomcat.apache.org/maven-plugin-trunk/tomcat7-maven-plugin/run-mojo.html#serverXml](http://tomcat.apache.org/maven-plugin-trunk/tomcat7-maven-plugin/run-mojo.html#serverXml)
