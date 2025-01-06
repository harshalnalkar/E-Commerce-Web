# E-Commerce Project (Spring Boot)

## Old Version
[GitHub Repository - Old Version](https://github.com/harshalnalkar/E-commerce-project-springBoot/tree/main)
- **Issue**: Database connection was opened and closed repeatedly for each access.

## New Version (What's New)
- **Hibernate Configuration Added**: Database and tables are automatically created when the project runs.
- **Service Classes**: Reusable services are provided throughout the project.
- **DAO Classes**: Dedicated classes to interact with the database.
- **Bug Fixes**: Fixed issues related to product images, security, etc.
- **IDE Support**: Works with both Eclipse and IntelliJ IDEA.
- **Code Redesign**: Improved overall code structure to enhance reusability.
- **Disclaimer**: This branch is a work in progress. There might be some bugs related to endpoints, and work is ongoing for cart logic.

## Quickstart

1. **Clone the Repository**
2. **Open the Project in Your IDE**:
   - For IntelliJ IDEA: Ensure the project opens as a **Maven** project and is recognized as a Spring Boot project. Update the working directory for proper view handling (check the [Web Directories](#web-directories) section).
3. **Navigate to the `JtProject` Directory**
4. **Configure Database Connection**:
   - Update the `application.properties` file (see [Database](#database) section for details).
5. **Run the Project**:
   - Run the `main` method in `JtSpringProjectApplication.java`.
6. **Access the Application**:
   - Open [http://localhost:8080/](http://localhost:8080/) in your browser.

   Example Login Credentials:
   - **Admin**: Username: `admin`, Password: `123` (if `basedata.sql` is executed).
   - **Normal User**: Username: `lisa`, Password: `765`.

### Database

MySQL or MariaDB is used as the database for this project. Configure the `src/main/resources/application.properties` file with the following properties:

```properties
db.url=jdbc:mysql://[ip address of db]:[port of db]/ecommjava?createDatabaseIfNotExist=true
db.username=[username]
db.password=[password, if any]
```

> **Note**: Avoid using the `root` user. Ensure the user has proper database permissions.

If you encounter the error `java.lang.IllegalArgumentException: Could not resolve placeholder 'db.driver'`, ensure the `mysql-connector-java` version in `pom.xml` matches your MySQL version. Reload the Maven project afterward.

To populate base data, run the `basedata.sql` script on your database.

### Web Directories

The views are located in `src/main/webapp/views`. Spring Boot may not recognize this directory by default. To fix this in IntelliJ IDEA:

1. Click **Edit Configurations**.
2. Select the `JtSpringProjectApplication` configuration.
3. Set the "Working directory" to `$MODULE_WORKING_DIR$`.
4. Apply and run the project.

The login page will be accessible at [http://localhost:8080/](http://localhost:8080/) if the above steps are correctly followed.

### Workflow

- **Controller**: Manages endpoints and sends data to the view using `ModelAndView`.
  ```java
  @GetMapping("login")
  public String adminlogin() {
      return "adminlogin";
  }
  ```
  
  When `/login` is accessed, `src/main/webapp/adminlogin.jsp` is executed.

- **Models**: Represent data as entities and define relationships between them.

- **View**: Receives data from the controller and presents it in the frontend.

## Endpoints
- [http://localhost:8080/](http://localhost:8080/)
- [http://localhost:8080/register](http://localhost:8080/register)
- [http://localhost:8080/admin/products](http://localhost:8080/admin/products)
- [http://localhost:8080/admin/customers](http://localhost:8080/admin/customers)
- [http://localhost:8080/admin/categories](http://localhost:8080/admin/categories)
- [http://localhost:8080/admin/Dashboard](http://localhost:8080/admin/Dashboard)

## Spring Boot

For more information about Spring Boot, refer to the following:

### Reference Documentation
- [Apache Maven Documentation](https://maven.apache.org/guides/index.html)
- [Spring Boot Maven Plugin Guide](https://docs.spring.io/spring-boot/docs/2.6.4/maven-plugin/reference/html/)
- [Spring Web Documentation](https://docs.spring.io/spring-boot/docs/2.6.4/reference/htmlsingle/#boot-features-developing-web-applications)

### Guides
- [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
- [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
- [Building REST Services with Spring](https://spring.io/guides/tutorials/bookmarks/)

## Preview

![Preview Image 1](https://github.com/harshalnalkar/E-Commerce-Web/assets/81226571/02a04d3c-1fc9-418c-b231-639f6525d07e)
![Preview Image 2](https://github.com/harshalnalkar/E-Commerce-Web/assets/81226571/24c4451b-43a6-4c23-a78a-786eab4303b0)
![Preview Image 3](https://github.com/harshalnalkar/E-Commerce-Web/assets/81226571/93c1baeb-326c-450f-867e-a883900a6644)

