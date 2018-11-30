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

```
	
		<!-- swagger-springmvc -->
    <dependency>
        <groupId>com.mangofactory</groupId>
        <artifactId>swagger-springmvc</artifactId>
        <version>1.0.2</version>
    </dependency>
    <dependency>
        <groupId>com.mangofactory</groupId>
        <artifactId>swagger-models</artifactId>
        <version>1.0.2</version>
    </dependency>
    <dependency>
        <groupId>com.wordnik</groupId>
        <artifactId>swagger-annotations</artifactId>
        <version>1.3.11</version>
    </dependency>



```

```

package com.aurfy.haze.web.spring;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Bean;
import org.springframework.web.servlet.config.annotation.ResourceHandlerRegistry;

import com.mangofactory.swagger.configuration.SpringSwaggerConfig;
import com.mangofactory.swagger.models.dto.ApiInfo;
import com.mangofactory.swagger.plugin.SwaggerSpringMvcPlugin;

/**
 * 
 * @author zhangcheng
 *
 */
public class SwaggerConfig extends WebConfigTemplate{

    private SpringSwaggerConfig springSwaggerConfig;

    /**
     * Required to autowire SpringSwaggerConfig
     */
    @Autowired
    public void setSpringSwaggerConfig(SpringSwaggerConfig springSwaggerConfig)
    {
        this.springSwaggerConfig = springSwaggerConfig;
    }

    /**
     * Every SwaggerSpringMvcPlugin bean is picked up by the swagger-mvc
     * framework - allowing for multiple swagger groups i.e. same code base
     * multiple swagger resource listings.
     */
    @Bean
    public SwaggerSpringMvcPlugin customImplementation()
    {
        return new SwaggerSpringMvcPlugin(this.springSwaggerConfig)
                .apiInfo(apiInfo())
                .includePatterns(".*?");
    }

    private ApiInfo apiInfo()
    {
        ApiInfo apiInfo = new ApiInfo(
                "My Apps API Title",
                "My Apps API Description",
                "My Apps API terms of service",
                "My Apps API Contact Email",
                "My Apps API Licence Type",
                "My Apps API License URL");
        return apiInfo;
    }
    
	@Override
	public void addResourceHandlers(ResourceHandlerRegistry registry) {
		registry.addResourceHandler("/swagger/**").addResourceLocations("/swagger/").setCachePeriod(31556926);
	}
}

```