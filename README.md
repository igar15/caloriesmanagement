[![Codacy Badge](https://app.codacy.com/project/badge/Grade/a806d20000d6447a855258744dd00dae)](https://www.codacy.com/gh/ishlyakhtenkov/caloriesmanagement/dashboard)
[![Build Status](https://api.travis-ci.com/ishlyakhtenkov/caloriesmanagement.svg?branch=master)](https://travis-ci.com//ishlyakhtenkov/caloriesmanagement)

Calories Management System project 
=================================

Java Enterprise project with registration / authorization and role-based access rights (USER, ADMIN). The administrator can create / edit / delete users, and users can manage their profile and data (food) via UI (via AJAX) and via REST interface with basic authorization.  
For training purposes, various methods of storing information in relational databases were used: JPA (Hibernate), Spring Data JBDC, Spring Data JPA (Hibernate). 

### Technology stack used: 
* Maven
* Spring MVC
* JPA (Hibernate)
* Spring Data JBDC
* Spring Data JPA (Hibernate)
* Spring Security
* Ehcache
* REST (Jackson)
* JUnit 5
* JSP
* JSTL
* jQuery + plugins
* DataTables
* Bootstrap 4
* OpenAPI 2

### Project key logic:
* System main purpose: users register in the application, after which it becomes possible for them to enter information about the food eaten and the number of calories it contains.
* There are 2 types of users: admins, authorized users.
* Authorized users can create/update/delete meals. Also, they can manage their profile and change their password.
* If the number of calories consumed exceeds the set daily value, the entered food will be highlighted in red.
* Admins have the same capabilities as authorized users. Moreover, they can create/update/block/delete users.

### Caching strategy
#### Spring caching (Ehcache provider):
- Get all users (singleNonExpiryCache, evicts when create/update/enable/delete any user)

#### Hibernate 2nd level cache:
- User entity (CacheConcurrencyStrategy: NONSTRICT_READ_WRITE)
