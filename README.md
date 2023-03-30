# Dockerize-a-Java-Web-Application-using-docker-compose-(project:04)


## Table of Contents

    1. Goal
    2. Pre-Requisites
    3. Docker-Compose
    4. Validation


![aws04](https://user-images.githubusercontent.com/47071968/228781491-14845b03-e986-4ab2-aa46-00ac90e91a43.jpeg)

## Goal

Goal of this project to deploy Java application stack (Nginx, Tomcat, MySQL) using docker-compose.


## Pre-Requisites

    1. Java login application source code is committed to the Bitbucket repo.
    2. Customize application.properties file with MySQL database name and credentials to connect with database.
    3. Build the Java source code and keep the artifact ready (.war)


## Docker-Compose

Write Docker-Compose YAML file to deploy Nginx, Tomcat, MySQL application  containers.

## Nginx:

    Customize Nginx application using source image “docker.io/nginx” and volume map nginx.conf to proxy the requests to the Tomcat application container.
    Expose port 80

## Tomcat:

    1. Customize Tomcat application using source image “docker.io/amazonlinux” and volume map tomcat-users.xml and .war artifact to serve the Java login application.
    2. Expose port 8080
    3. Install Java, mysql, telnet packages.

## MySQL:

    1. Customize MySQL application using source image” docker.io/mysql” and add environment variables to setup database name and passwords.
    2. Expose port 3306.
    3. Create Table Schema on container startup;  Bitbucket repo README.md file updated with the Table Schema details compatible for the Login application.


## Validation

    1. Ensure containers are running and healthy.
    2. Login to Tomcat container and check the MySQL access using “mysql” client cli.
    3. Create hosted zone in AWS Route 53 and add A record pointing to the EC2 instance Elastic IP.
    4. Verify application is accessible using public internet browser.
