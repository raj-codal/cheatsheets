
Spring boot starters :
	SOAP,RESTful,test,jdbc,hateoas,security,data-jpa,cache,data-rest

---------------
Annotations :

@controller annotation for making a spring -- Controller -- on a class

@RequestMapping({urls,....}) for making a spring servlet based controller

@ResponseBody for making the type of response based on return type ... like 

public String hello(){
 return "helloworld";
} 
-- returns a string in response. --

@PostConstruct for calling a method/function as a once after the application is started

@Component, @Value, @Order

@component :
	make a bean from a class (a factory model)

@Autowire :
	It tries to search the specified bean type and create an object of that bean and passes to the given reference

@Primary :
	If an interface (@component) is implemented by more than one class and we want to make sure that this class is used by spring instead of other, we use @Primary annotation and make it Primary.

@PathVariable :
	Used to extract the values in given in the URL
	EG.

		@GetMapping(path="/path/{name}")
		public TestBean point2(@PathVariable String name){
			return new TestBean(name);
		}

@Requestbody :

	It maps the request body to the passed object 

ResponseEntity<T> :

	@PostMapping("/add-user")
    public ResponseEntity<Object> createUser(@RequestBody User user){
        User savedUser = service.save(user);

        URI location = ServletUriComponentsBuilder
                .fromCurrentContextPath().path("/user/{id}")
                .buildAndExpand(savedUser.getId()).toUri();
        System.out.println(location.toString());

        return ResponseEntity.created(location).build();
    }

--- tools ---
Actuator : 
	for monitoring the spring apis (Complete website from the browser).



--- Spring Boot Secrity ---

@WebSecurity
class xyz extends WebSecurityConfigurerAdapter{

//Authentication
@Override
protected void configure(AuthenticationManagerBuilder auth){
//
}


//Authorization
@Override
protected void configure(HttpSecurity http){
//
}

}

Authentication - {Username, Password}

	- Knowledge Based --- passwords and pins
	- Possession Based --- google phone based auth.
	- Multi Factor

	

Authorization - {JWT, auth_keys} 

Principal - currently logged in user

Role - gives/defines permission to users
	- Group of permissions/Authorities




--- configs ---

Jackson serialization is used for object to JSON conversion and vice versa




--- Http Configs ---

200 OK
201 Resource Created

400 Bad request
404 Not Found
406 Content not supported (Format error)

500 Internal server error


--- HateAoS ---

It is used to send the resouces more robust. like if we want to send other links along with the user resource we can use the HATEAOS...

//

{
	DATA: MAP<>
	MSG: String
	Success: False
	TimeStamp: Int
	StatusCode: Int
}

Check @Required/@NotNull