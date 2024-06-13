# E-commerce-project-springBoot
This a web application Java Based Beginner level project To developing the e-commerce website to Buy/sell the Food Item. We use the Spring Boot to build the back-end part

Clone the repository
Open the project in your IDE: IntelliJ IDEA (recommended) or Eclipse
If you are using IntelliJ IDEA, make sure the IDE opens project as Maven and recognizes the project as a Spring Boot project. Also, you must change the working directory of the project so that the views (the actual web pages to be shown) are found by Spring Boot (check out Web Directories IntelliJ IDEA.
Make sure you are in the JtProject directory
Configure the database connection in application.properties file (check the Database section below for more info)
Run the project (by running the main method in JtSpringProjectApplication.java)
Open http://localhost:8080/ in your browser!
If you ran the basedata.sqlscript on the database, you can log in with the following credentials as admin; otherwise you'll have to manually create an admin user in the database:
Username: admin
Password: 123
Log in as a normal user:
Username: lisa
Password: 765
Database
MySQL or MariaDB can be used as the database for this project. The database connection can be configured in the application.properties file, with the appropriate values for the following properties: (you'd better use another username not root)

    db.url=jdbc:mysql://[ip address of db]:[port of db]/ecommjava?createDatabaseIfNotExist=true
    db.username=[username]
    db.password=[password, if any]
if you met the error java.lang.IllegalArgumentException: Could not resolve placeholder 'db.driver' in value "${db.driver}", maybe you should change your mysql-connector-java version in pom.xml file according to your mysql version, don't forget to reload your Maven project.

Having done that, you must create some base data in the database. You can do that by running the basedata.sql script on the database. Check out Google for how to do that, because it depends on what tool you are using to access said database.

Web Directories
The views are located in src/main/webapp/views, but for some reason, Spring Boot doesn't recognize that directory. To remedy this, you must change the working directory of the project in your IDE. If you're using IntelliJ IDEA, follow these steps:

Click on the "Edit Configurations..." button in the top right corner of the IDE
Click on the JtSpringProjectApplication configuration
Change the "Working directory" option (if not present, click on "Modify Options" and select from the list) to the $MODULE_WORKING_DIR$ macro
Click "Apply" and "OK"
When you run the project, the views should be found by Spring Boot and you should see a login page in http://localhost:8080/ (if not logged in previously)! configurations

Workflow
image
Controller
control the endpoint and also send data to view( we use ModelAndView method)
  public String adminlogin() {
  	
  	return "adminlogin";
  }```
whenever /login url is hit , src->main->webapp-> adminlogin.jsp file execute
Models
represent data as entity and relationship among them.
View
receive data from controller and show with frontend.
Endpoints
http://localhost:8080/
http://localhost:8080/register
http://localhost:8080/admin/products
http://localhost:8080/admin/customers
http://localhost:8080/admin/categories
http://localhost:8080/admin/Dashboard
Spring Boot
For any information about Spring Boot, here are some useful links!
