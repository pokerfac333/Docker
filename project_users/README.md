<p align="center">
<a target="blank"><img align="center" src="https://img.icons8.com/color/344/docker.png" alt="Shell" height="100" /></a>
</p>

<h2 align="center">This project in a docker with python application knows how to save users with lastName and firstName and display user data on request with id 💻</h2>

## 📀 How it's work :

+ ✅ Dockerfile installs dependencies from requirements.txt file
+ ✅ Application is available on port 8000
+ ✅ Application works on behalf of the user app
+ ✅ Working directory in the container is /app path
+ ✅ There are two services in docker-compose.yml file - db (postgres) and app.
+ ✅ Application is built automatically when docker-compose up command is executed
+ ✅ Application is launched from local project files



### The app knows how to save users with lastName and firstName and display user data by query with id

#### Functionality can be checked with queries:

```
curl localhost:8000/api/v1/users -X POST -d '{"firstName":"John","lastName":"Cena"}' --header "Content-Type: application/json"
```

#### Sample answer:

```
{
  "user": {
    "firstName": "John",
    "id": 1,
    "lastName": "Cena"
  }
}
```
#### Request:

```
curl localhost:8000/api/v1/users/1
```
#### Sample answer:

```
{
  "user": {
    "firstName": "John",
    "id": 1,
    "lastName": "Cena"
  }
}
```