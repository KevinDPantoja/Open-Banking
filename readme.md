# Open Banking

## Configuración necesaria para interactuar con APIs de Open Bank Project

A fin de hacer uso de las APIs de open bank project se requiere hacer una configuracion inicial. A continuacion se define la configuracion necesaria:

### **1**. Ingresar en [openbankproject.com/](https://apisandbox.openbankproject.com/ "Open Bank Project")
   
### **2**. Crear una cuenta
   
![Register](img/Register.png "Register")


### **3**. Obtener un API Key

![GetAPIKey](img/GetAPIKey.png "GetAPIKey")

Despues de obtener un API Key deberia llegar un correo electronico de confirmacion al correo que se uso para crear la cuenta en Open Bank Project


![image](https://github.com/KevinDPantoja/Open-Banking/assets/117990470/b6e1936b-33fd-4186-9c78-c70265262862)


**IMPORTANTE**, se debe guardar el *Consumer Key* y el *Consumer Secret* en un lugar seguro ya que no va a ser posible volver a conseguirlos despues y por lo tanto habria que borrar la aplicacion y volver a crear otra.


### **4**.   Autenticarse

Hay por lo menos dos opciones para probar las APIs:


* En Postman
* Directamente en la pagina de Open Bank Project


Si uno desea hacerlo en Postman es necesario autenticarse por medio de la creacion de un token, el cual permite un logueo desde Postman. Pero si vamos a hacer pruebas directamente desde la pagina de Postman no hace falta hacer la creacion del token, pues en el momento que uno inicia sesion ya cuenta como un usuario logueado. 


#### **4.1**.  Autenticacion en Postman

A la fecha(2/11/2023) en la documentacion aparece esta guia:

![Authenticate](img/Authenticate.png "Authenticate")

Tenengamos en cuenta que tal como indica la documentacion unicamente se debe ingresar el endpoint POST *https://apisandbox.openbankproject.com/my/logins/direct*  y ingresar en el Header los dos parametros Content-Type y directlogin, por lo tanto no hace falta ingresar ningun dato adicional en Params, Authorization( el cual se puede dejar en type como inherith auth from parent), body, pre-request Script, Test, Settings. Si llevamos esto a Postman quedaria de esta forma:


![Authenticate1](img/Authenticate1.png "Authenticate1")



Tengamos en cuenta que este Username y el password son los que se usaron para la creacion de la cuenta ( en el paso 2) de este tutorial) tal como indica la documentacion unicamente se debe ingresar el endpoint POST *https://apisandbox.openbankproject.com/my/logins/direct*  y ingresar los dos parametros Content-Type y directlogin.

#### **4.2**.  Creacion de token

Despues de ejecutar el request se deberia obtener lo siguiente:


![Token](img/Token.png "Token")


Este token se usara posteriormente en el llamado de las demas APIs de Open Bank Project en Postman, como se menciono previamente, en caso  de que se hagan pruebas directamente en la pagina de Open Bank Project no sera necesario generar este token pues al iniciar sesion ya se cuenta como un usuario autenticado.


### **5**.   Obtener Rol CanCreateBank 

En el proceso de prueba y error pude ver que lo mas practico a fin de hacer llamados 200 era usar un endpoint para crear un banco y luego de crear el banco ya se podia proceder con las demas pruebas de las APIs, actualmente (2/11/2023) Open Bank Project tiene 587 APIs, pero una forma sencilla de empezar es usar la API llamada Create Bank

![CreateBank](img/CreateBank.png "CreateBank")

Con esta API podremos crear un banco y de ahi para adelante sera posible proceder con la creacion de clientes, cuentas, tarjetas y demas productos que estaran vinculados especificamente a ese banco. Sin embargo, un requisito importante para poder crear un banco es tener un rol llamado **CanCreateBank**. Entonces ¿Como se puede obtener ese rol?, 
una forma de lograrlo  es dirigirnos a la pagina principal de Open Bank Project y buscar la seccion de support:

![image](https://github.com/KevinDPantoja/Open-Banking/assets/117990470/5e10659c-a33a-42d8-9b4f-839f69ed71db)



Estando dentro del chat general se puede solicitar ayuda pidiendo a alguno de los asesores que nos permitan tener el rol de **CanCreateBank**


![image](https://github.com/KevinDPantoja/Open-Banking/assets/117990470/adabbfd5-4771-435e-b8b8-65e016a7d0bb)


Luego de eso es cuestion de esperar la respuesta de alguno de los asesores ya que sin este rol no es posible proceder con las pruebas pero en el momento que recibimos ese rol recibiremos un correo electronico que se ve de esta forma:


![image](https://github.com/KevinDPantoja/Open-Banking/assets/117990470/686d0748-64a1-4144-bf82-b66a5e34234d)



Ya teniendo ese rol podemos proceder a hacer la creacion de un banco usando las APIs de Open Bank Project. Hay por lo menos dos formas de hacer esto:

* En Postman
* En la pagina de Open Bank Project


Veamos la forma de hacerlo en Postman:

1) Procedemos a configurar el Header:

  
























 

 

