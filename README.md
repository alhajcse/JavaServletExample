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
4. Cearte a servlet class ***package com.alhaj.servletexample;

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
}***



