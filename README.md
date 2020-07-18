# spring-user-signin-jwt-functionality
sinup user:
post :  http://localhost:8011/users-ws/users
body:
<UserRest>
    <firatname>Ziad</firatname>
    <lastname>Jamal</lastname>
    <email>alaajamal470@gmail.com</email>
    <password>154454588</password>
</UserRest>

login user:
post : http://localhost:8011/users-ws/users/login
body : 
{
    "email":"alaajamal470@gmail.com",
    "password":"154454588"
}
steps of running users web service:

1. When we trigger our spring service, the spring framework will call configure method to configure the FilterManagerBuilder in which we register two params :
	a. UserDetailsService class which is Userservice to use loadUserByUsername on each login request.
	b. Bcryppassword class which we used to store our passwordhash.
2. Then spring will register our filter in httpsecurity.

3. When login request comes,then spring will call attemptAuthentication method which will call getAuthenticationManager to get AuthenticationManager that we have registered. This manager will call loadUserByUsername method to get User object that have the valid token and compare it with which embadded in the UsernamePasswordAuthenticationToken object.

4.If the authentication is successful then spring framework will call successfulAuthentication method in this method we generate JWT token using apache json web token dependency and add this token with userId to the response header.
