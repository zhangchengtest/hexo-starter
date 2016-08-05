title: spring security改变默认登陆页面
date: 2016-04-10 11:44:10
tags:
---
title: spring security改变默认登陆页面
tags:
---

参考链接
[http://docs.spring.io/spring-security/site/docs/3.2.x/guides/form.html](http://docs.spring.io/spring-security/site/docs/3.2.x/guides/form.html)

自定义登陆方法
[http://spr.com/part-5-integrating-spring-security-with-spring-boot-web/](http://spr.com/part-5-integrating-spring-security-with-spring-boot-web/)

有12个默认的拦截器
```java
[
org.springframework.security.web.context.request.async.WebAsyncManagerIntegrationFilter@161876d
 org.springframework.security.web.context.SecurityContextPersistenceFilter@934246
 org.springframework.security.web.header.HeaderWriterFilter@11be4a
 org.springframework.security.web.csrf.CsrfFilter@29452
 org.springframework.security.web.authentication.logout.LogoutFilter@94b17e
 org.springframework.security.web.authentication.UsernamePasswordAuthenticationFilter@10ceac
 org.springframework.security.web.authentication.ui.DefaultLoginPageGeneratingFilter@730c0f
 org.springframework.security.web.savedrequest.RequestCacheAwareFilter@1e40d3e
 org.springframework.security.web.servletapi.SecurityContextHolderAwareRequestFilter@12170c6
 org.springframework.security.web.session.SessionManagementFilter@e41e92
 org.springframework.security.web.access.ExceptionTranslationFilter@c94dc8
 org.springframework.security.web.access.intercept.FilterSecurityInterceptor@f40b6
 ]
```
access deny
```java
org.springframework.security.web.access.expression.DefaultWebSecurityExpressionHandler@91f79a
```