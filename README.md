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
