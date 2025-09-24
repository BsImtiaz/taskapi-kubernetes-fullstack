# Task-1.-Java-backend-and-REST-API-example.
This project is a Task Management REST API built using Java and Spring Boot. It demonstrates how to create, read, search, execute, and delete tasks using RESTful endpoints. All data is stored in-memory for demonstration purposes, and the API is tested using Postman.

# Technologies Used
1.Java (JDK 17 or above)
2.Spring Boot (latest stable version)
3.Maven (for build and dependency management)

# Features
Create a Task: Add a new task with a unique ID, name, owner, and command.
Get All Tasks: Retrieve a list of all tasks.
Get Task by ID: Fetch details of a specific task using its ID.
Search Tasks by Name: Find tasks whose names contain a given substring.
Execute a Task: Run the command associated with a task and store the execution result.
Delete a Task: Remove a task by its ID.

# How to Run
In project folder, run: mvn spring-boot:run
API will be available at: http://localhost:8080

# Method	          Endpoint	                          Description
PUT              	/tasks              	            Create a new task
GET	              /tasks	                          Get all tasks
GET	            /tasks?id={id}	                    Get task by ID
GET	      /tasks/search?name={substring}	          Search tasks by name
PUT       	/tasks/{id}/executions                	Execute a task
DELETE	        /tasks/{id}	                        Delete a task
