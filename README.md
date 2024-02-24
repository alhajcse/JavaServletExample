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
Let’s go ahead and add such users by editing the conf/tomcat-users file:

  <tomcat-users>
  <role rolename="manager-gui"/>
  <role rolename="manager-script"/>
  <user username="admin" password="123456" roles="manager-gui,manager-script"/>
  </tomcat-users>


9. Let’s open http://localhost:8080/manager/html/ to view the Tomcat Manager App webpage.
 ![tomcat-manager-app-e1570014354196 (1)](https://github.com/alhajcse/JavaServletExample/assets/50860728/616718f3-818d-4bab-b329-fd89312df714)

 








