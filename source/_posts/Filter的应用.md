title: Filter的应用
date: 2016-04-10 10:52:40
tags:
---
title: Filter的应用
tags:
---

VirtualFilterChain
含有12个拦截器
当是登陆请求路径的时候即login
DefaultLoginPageGeneratingFilter
```java
public void doFilter(ServletRequest req, ServletResponse res, FilterChain chain)
			throws IOException, ServletException {
		HttpServletRequest request = (HttpServletRequest) req;
		HttpServletResponse response = (HttpServletResponse) res;

		boolean loginError = isErrorPage(request);
		boolean logoutSuccess = isLogoutSuccess(request);
		if (isLoginUrlRequest(request) || loginError || logoutSuccess) {
			String loginPageHtml = generateLoginPageHtml(request, loginError,
					logoutSuccess);
			response.setContentType("text/html;charset=UTF-8");
			response.setContentLength(loginPageHtml.length());
			response.getWriter().write(loginPageHtml);

			return;
		}

		chain.doFilter(request, response);
	}
```
当不是登陆的路径 应该重定向
通过ExceptionTranslationFilter可以重定向， 通过重定向
```java

			if (ase != null) {
				handleSpringSecurityException(request, response, chain, ase);
			}
```



ApplicationFilterChain