Node.js, Express & MySQL: Simple Add, Edit, Delete, View (CRUD)
========

A simple and basic CRUD application (Create, Read, Update, Delete) using Node.js, Express, MySQL & EJS Templating Engine.

**Blog:** [Node.js, Express & MySQL: Simple Add, Edit, Delete, View (CRUD)](http://blog.chapagain.com.np/node-js-express-mysql-simple-add-edit-delete-view-crud/)

**Creating database and table**

```
create database test;

use test;

CREATE TABLE users (
id int(11) NOT NULL auto_increment,
name varchar(100) NOT NULL,
age int(3) NOT NULL,
email varchar(100) NOT NULL,
PRIMARY KEY (id)
);
```

# Steps to deploy

1. Make sure k8s cluster is running and kubectl is pointed to the cluster
1. Run above sql commands to create test DB
1. Update `config.js.sample` with the actual values and save it as `config.js`
1. Create a configmap `nodejs-mysql-crud-map` with file `config.js`
1. Create a tls secret `tls-secret` for the hosts. You an use a self signed cert
1. Run the following to deploy the app
```shell
kubectl apply -f deployment.yaml
```

# Steps to access site
1. Access the app via https://HOST

