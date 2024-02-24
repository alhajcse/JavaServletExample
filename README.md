# Java Servlet

# Servlet
Servlet is a java object that can read/understand HTTP requet and get response according to request.

# Hello World Servlet for tomcat-9
1. Create empty project intellij idea with gradle
2. Add Dependency  ***compileOnly 'javax.servlet:javax.servlet-api:4.0.1'***
3. Add ***id 'war'*** In plugins {
    id 'java'
    id 'war'
}

group 'com.alhaj.servlet'
version '1.0'

repositories {
    mavenCentral()
}

ext {
    junitVersion = '5.9.2'
}

sourceCompatibility = '11'
targetCompatibility = '11'

tasks.withType(JavaCompile) {
    options.encoding = 'UTF-8'
}

dependencies {
    compileOnly 'javax.servlet:javax.servlet-api:4.0.1'
    testImplementation("org.junit.jupiter:junit-jupiter-api:${junitVersion}")
    testRuntimeOnly("org.junit.jupiter:junit-jupiter-engine:${junitVersion}")
}

test {
    useJUnitPlatform()
}



