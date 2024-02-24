# Java Servlet

# Servlet
Servlet is a java object that can read/understand HTTP requet and get response according to request.

# Hello World Servlet for tomcat-9
1. Create empty project intellij idea with gradle
2. Add Dependency  ***compileOnly 'javax.servlet:javax.servlet-api:4.0.1'***
3. Add ***id 'war'***
   In build.gradle plugins {
    id 'java'
    id 'war'
}
4. Cearte a servlet class ***MyWebServlet**
package com.alhaj.servletexample;
import javax.servlet.ServletException;
import javax.servlet.http.*;
import java.io.IOException;
import java.io.PrintWriter;

public class MyWebServlet extends HttpServlet {

    public void doGet(HttpServletRequest request, HttpServletResponse response)
            throws IOException, ServletException
    {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("<html>");
        out.println("<head>");
        out.println("<title>Hello World!</title>");
        out.println("</head>");
        out.println("<body>");
        out.println("<h1>Hello World!</h1>");
        out.println("</body>");
        out.println("</html>");
    }
}

5. Add Mapping in **webapp/WEB-INFO/web.xml** file

<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"
         version="4.0">
   <servlet>
        <servlet-name>MyWevServlet</servlet-name>
        <servlet-class>com.alhaj.servletexample.MyWebServlet</servlet-class>
    </servlet>

    <servlet-mapping>
        <servlet-name>MyWevServlet</servlet-name>
        <url-pattern>/hello_world</url-pattern>
    </servlet-mapping>
</web-app>


6. Install apache tomcat
7. Accessing the Tomcat Manager App
Let’s go ahead and add such users by editing the **conf/tomcat-users**
   *** <tomcat-users>
  <role rolename="manager-gui"/>
  <role rolename="manager-script"/>
  <user username="admin" password="123456" roles="manager-gui,manager-script"/>
  </tomcat-users>
  ***


9. Let’s open http://localhost:8080/manager/html/ to view the Tomcat Manager App webpage.
![image-112-1024x707](https://github.com/alhajcse/JavaServletExample/assets/50860728/fd6864ad-59eb-4a77-82da-6b52696374e8)

10. Build war file for deploy in application manager
    **./gradlew war**

11. Another way to locally run, application connect to tomcat server
    
<img width="848" alt="Screenshot 2024-02-24 at 8 08 13 PM" src="https://github.com/alhajcse/JavaServletExample/assets/50860728/20da03a4-5baa-4c87-a953-6ceccc970821">

<img width="844" alt="Screenshot 2024-02-24 at 8 08 51 PM" src="https://github.com/alhajcse/JavaServletExample/assets/50860728/15fe0a7b-ed21-4934-9dea-bc2cc4f1304c">

12. Finally run and view the application
<img width="1277" alt="Screenshot 2024-02-24 at 11 28 12 PM" src="https://github.com/alhajcse/JavaServletExample/assets/50860728/ea4cd5d3-0eaa-4371-b39a-b2986316cdea">

 








