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

5. Add Mapping in **webapp/WEB-INFO/web.xml**

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




