# HTTP 상태 500 – 내부 서버 오류

- jsp에서 `getBookList()`메서드를 호출 하려고 했는데 `oracle.jdbc.OracleDriver`에러가 발생 했다...
- 원인
  - 해당 원이는 jdbc 라이브러리를 사용 할 수 있는 `ojdbc6.jar`파일이 존재하지 않기 때문이였다...
- 해결 방법
  -  `ojdbc6.jar`파일을  `WEB-INF/lib/`추가  하면 문제가 해결된다. 
- 결론
  - 너무 단순한 문제였지만.. :sweat: 간단한 에러는 되풀이 되지 않게 자바에서 DB 접근할 일이 있을 땐 꼭 `ojdbc6.jar`파일을 프로젝트에 있는지 확인하자!! :+1::+1:

```
HTTP 상태 500 – 내부 서버 오류


타입 예외 보고

메시지 행 [15]에서 [day22/connect.jsp]을(를) 처리하는 중 예외 발생

설명 서버가, 해당 요청을 충족시키지 못하게 하는 예기치 않은 조건을 맞닥뜨렸습니다.

예외
org.apache.jasper.JasperException: 행 [15]에서 [day22/connect.jsp]을(를) 처리하는 중 예외 발생

12: <body>
13: <% 
14:    BookTest bt = new BookTest();
15:    ArrayList<BookDTO> list = bt.getBookList();
16:    for(BookDTO dto : list){
17:       out.print("<h1>"+dto.getTitle()+"</h1>");
18:    }


Stacktrace:
	org.apache.jasper.servlet.JspServletWrapper.handleJspException(JspServletWrapper.java:611)
	org.apache.jasper.servlet.JspServletWrapper.service(JspServletWrapper.java:490)
	org.apache.jasper.servlet.JspServlet.serviceJspFile(JspServlet.java:378)
	org.apache.jasper.servlet.JspServlet.service(JspServlet.java:326)
	javax.servlet.http.HttpServlet.service(HttpServlet.java:733)
	org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:53)


근본 원인 (root cause)
java.lang.ClassNotFoundException: oracle.jdbc.OracleDriver
	org.apache.catalina.loader.WebappClassLoaderBase.loadClass(WebappClassLoaderBase.java:1364)
	org.apache.catalina.loader.WebappClassLoaderBase.loadClass(WebappClassLoaderBase.java:1187)
	java.base/java.lang.Class.forName0(Native Method)
	java.base/java.lang.Class.forName(Class.java:377)
	mc.sn.test2.BookTest.getConnection(BookTest.java:60)
	mc.sn.test2.BookTest.getBookList(BookTest.java:14)
	org.apache.jsp.day22.connect_jsp._jspService(connect_jsp.java:135)
	org.apache.jasper.runtime.HttpJspBase.service(HttpJspBase.java:71)
	javax.servlet.http.HttpServlet.service(HttpServlet.java:733)
	org.apache.jasper.servlet.JspServletWrapper.service(JspServletWrapper.java:467)
	org.apache.jasper.servlet.JspServlet.serviceJspFile(JspServlet.java:378)
	org.apache.jasper.servlet.JspServlet.service(JspServlet.java:326)
	javax.servlet.http.HttpServlet.service(HttpServlet.java:733)
	org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:53)


비고 근본 원인(root cause)의 풀 스택 트레이스를, 서버 로그들에서 확인할 수 있습니다.


Apache Tomcat/9.0.45
```



