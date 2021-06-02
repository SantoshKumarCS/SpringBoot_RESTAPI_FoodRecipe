# SpringBoot_RESTAPI_FoodRecipe
Application which allows user to manage food recipes using SpringBoot, Microservice, RESTAPI, Swagger, Spring security.

Tools/Technologies used:
•	Spring Tool Suite 4
•	Java 1.8 
•	Maven
•	Spring Boot 2.4.5
•	Rest API
•	Microservices
•	MySQL database
•	POSTMAN

API’s to show all available recipes and the actions to create, update and delete a recipe.
POSTMAN tool is used to test the APIs created.
1.	Add Recipe API: http://localhost:8080/recipe/add
Both user and admin role has access for this API.
Sample Body:
{
	"recipeName":"Masala Dosas",
	"createdDate":"01-06-2021 12:34",
	"isVeg":true,
	"suitableFor":"for everyone",
	"ingredients":[
		{
		"description": "half cup idli rice or parboiled rice or 100 grams idli rice"
		},
		{
		"description": "half cup regular rice or 100 grams regular rice"	
		},
		{
		"description": "2 tablespoon poha"
		}
	],
	"cooking instructions": "In a bowl take the idli rice or parboiled rice along with the regular white rice. Instead of adding regular rice, you can also make the dosa with a total of 1 cup idli rice as I have shown in the video. The video has the recipe ingredients doubled in proportion. To the same bowl, add urad dal and fenugreek seeds. Rinse the rice, lentils, and methi seeds together a couple of times and keep them aside. In a separate bowl, take the poha. Rinse it once or twice in water and then add rinsed poha to the bowl containing the rinsed rice+lentils+methi seeds. Pour 1.5 cups of water. Mix. Cover with a lid and soak everything for 5 to 6 hours."
}

2. List all the Recipes: http://localhost:8080/recipe/get
Both user and admin role has access for this api.
Sample Response:
[
    {
        "id": 1,
        "recipeName": "Masala Dosa",
        "createdDate": "01-06-2021 12:34",
        "isVeg": true,
        "suitableFor": "for everyone",
        "cookingInstructions": "In a bowl take the idli rice or parboiled rice along with the regular white rice. Instead of adding regular rice, you can also make the dosa with a total of 1 cup idli rice as I have shown in the video. The video has the recipe ingredients doubled in proportion. To the same bowl, add urad dal and fenugreek seeds. Rinse the rice, lentils and methi seeds together a couple of times and keep aside. In a separate bowl, take the poha. Rinse it once or twice in water and then add rinsed poha to the bowl containing the rinsed rice+lentils+methi seeds. Pour 1.5 cups water. Mix. Cover with a lid and soak everything for 5 to 6 hours.",
        "ingredients": [
            {
                "id": 1,
                "description": "half cup idli rice or parboiled rice or 100 grams idli rice"
            },
            {
                "id": 2,
                "description": "half cup regular rice or 100 grams regular rice"
            },
            {
                "id": 3,
                "description": "2 tablespoon poha"
            }
        ]
    }
]

3. Edit/Update Recipe API: http://localhost:8080/recipe/update
Only admin role has access for this api.
Sample Request Body:
{
    "id": 1,
    "recipeName": "Masala Dosas",
    "createdDate": "01-06-2021 12:25",
    "isVeg": false,
    "suitableFor": "for everyone",
    "cookingInstructions": "In a bowl take the idli rice or parboiled rice along with the regular white rice. Instead of adding regular rice, you can also make the dosa with a total of 1 cup idli rice as I have shown in the video. The video has the recipe ingredients doubled in proportion. To the same bowl, add urad dal and fenugreek seeds. Rinse the rice, lentils and methi seeds together a couple of times and keep aside. In a separate bowl, take the poha. Rinse it once or twice in water and then add rinsed poha to the bowl containing the rinsed rice+lentils+methi seeds. Pour 1.5 cups water. Mix. Cover with a lid and soak everything for 5 to 6 hours.",
    "ingredients": [
        {
            "id": 1,
            "description": "half cup idli rice or parboiled rice or 100 grams idli rice"
        },
        {
            "id": 2,
            "description": "half cup regular rice or 100 grams regular rice"
        },
        {
            "id": 3,
            "description": "2 tablespoon poha"
        }
    ]
}
 
4. Delete Recipe API : http://localhost:8080/recipe/delete/1
Only admin role has access to this API.
Credentials: username: admin, password: admin
Open Postman:
Provide delete request API to delete recipe added with providing basic authentication information.

Spring Boot dependencies added
<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-actuator</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		<dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<scope>runtime</scope>
			<version>8.0.25</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-security</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
		    <groupId>com.fasterxml.jackson.core</groupId>
		    <artifactId>jackson-core</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
		<dependency> 
		    <groupId>org.springframework.boot</groupId> 
		    <artifactId>spring-boot-starter-validation</artifactId> 
		</dependency>
		<dependency>
			<groupId>org.springframework.security</groupId>
			<artifactId>spring-security-test</artifactId>
			<scope>test</scope>
		</dependency>
		<dependency>
			<groupId>io.springfox</groupId>
			<artifactId>springfox-swagger2</artifactId>
			<version>2.7.0</version>
		</dependency>
		<dependency>
			<groupId>io.springfox</groupId>
			<artifactId>springfox-swagger-ui</artifactId>
			<version>2.7.0</version>
		</dependency>
	</dependencies>

Added Swagger dependency to illustrate the use of API in a single page i.e REST API Documentation
URL: http://localhost:8080/swaggerui-html
