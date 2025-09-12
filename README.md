![dePinhoLP](https://github.com/ICEI-PUC-Minas-PPLES-TI/plf-es-2024-1-ti3-8966100-de-pinho-multimidias/assets/119077937/657b04df-43b5-4973-8d3c-63e1c01cd9dd)

# DePinho Multimedia

DePinho Multimedia is a website designed to make it easier for customers of YouTuber Gabriel De Pinho to purchase new multimedia devices. The site offers product filtering options based on the customer’s car, displaying only the multimedia models compatible with their vehicle.

## Team Members

* Arthur Ferreira Costa
* Gabriel Ferreira Amaral
* Gabriel Pongelupe de Carvalho
* Pedro Henrique Braga de Castro
* Renato Cazzoletti

## Supervising Professors

* Eveline Alonso Veloso
* Juliana Amaral Baroni de Carvalho

## Usage Instructions

### Prerequisites

Make sure you have the following software installed on your machine:

* [Java Development Kit (JDK)](https://www.oracle.com/java/technologies/javase-downloads.html)
* [Apache Maven](https://maven.apache.org/)
* [MySQL](https://www.mysql.com/)

### Step-by-step Installation and Execution

#### 1. Clone the Repository

```bash
git clone https://github.com/ICEI-PUC-Minas-PPLES-TI/plf-es-2024-1-ti3-8966100-de-pinho-multimidias.git
cd plf-es-2024-1-ti3-8966100-de-pinho-multimidias
```

#### 2. Configure the Database

* Set your database credentials in the `application.properties` file located in `src/main/resources`:

  ```properties
  spring.datasource.username=your-username
  spring.datasource.password=your-password
  ```

#### 3. Update CORS Configuration

In the CORS configuration file, update the settings to allow the frontend running on localhost:8081:

```java
    .allowedOrigins("http://127.0.0.1:8081")
```

#### 4. Install Dependencies

In the project root directory, run:

```bash
mvn clean install
```

#### 5. Run the Application

Still in the root directory, run:

```bash
mvn spring-boot:run
```

The application will be running at [http://localhost:8080](http://localhost:8080).

### Usage

1. **Register and Login:**

   * Register as a new user or log in with your existing credentials.

2. **Browse Products:**

   * Use the filter to select your vehicle model and view compatible products.

3. **Add to Cart:**

   * Add desired products to your shopping cart.

4. **Checkout:**

   * Fill in the required payment details and complete your purchase.

### Admin Login

To log in as an administrator, you must send a request via Postman:

1. **Open Postman and create a new POST request.**
2. **URL:** `http://localhost:8080/usuario/register`
3. **Body:** Select `raw` and choose `JSON` format. Insert the admin credentials as follows:

   ```json
       {
         "email": "teste@123412",
         "senha": "luisa1234",
         "primeiroNome": "Gabriel",
         "ultimoNome": "Enzo",
         "contato": "(37) 12345-6789",
         "role": "ADMINISTRADOR"
       }
   ```
4. **Send the request.** After logging in with this user, a token will be generated in your browser’s LocalStorage. This token must be used in subsequent requests to access administrative features.
