@controller annotation for making a spring -- Controller -- on a class

@RequestMapping({urls,....}) for making a spring servlet based controller

@ResponseBody for making the type of response based on return type ... like 
public String hello(){
 return "helloworld";
} -- returns a string in response.

@PostConstruct for calling a method/function as a once after the application is started

@Component, @Value, @Order

--- Spring Boot Secrity ---

Authentication - {Username, Password}

	- Knowledge Based --- passwords and pins
	- Possession Based --- google phone based auth.
	- Multi Factor

Authorization - {JWT, auth_keys} 

Principal - currently logged in user

Role - gives/defines permission to users
	- Group of permissions/Authorities
