
Spring boot starters :
	SOAP,RESTful,test,jdbc,hateoas,security,data-jpa,cache,data-rest

---------------
Annotations :

@controller annotation for making a spring -- Controller -- on a class

@RequestMapping({urls,....}) for making a spring servlet based controller

@ResponseBody for making the type of response based on return type ... like 
public String hello(){
 return "helloworld";
} -- returns a string in response.

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


