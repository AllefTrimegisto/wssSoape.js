# wssSoape.js
Crie um servidor SOAP simples usando Java, disponibilize endpoints (métodos) e crie, no mínimo, quatro deles. Por fim, coloque para rodar na porta 8080.

import javax.jws.WebMethod;
import javax.jws.WebService;
import javax.xml.ws.Endpoint;

@WebService
public class Calculator {
   @WebMethod
   public int add(int a, int b) {
      return a + b;
   }
   
   @WebMethod
   public int subtract(int a, int b) {
      return a - b;
   }
   
   @WebMethod
   public int multiply(int a, int b) {
      return a * b;
   }
   
   @WebMethod
   public int divide(int a, int b) {
      return a / b;
   }
}

public class CalculatorPublisher {
   public static void main(String[] args) {
      Endpoint.publish("http://localhost:8080/calculator", new Calculator());
   }
}

Este exemplo cria uma classe chamada Calculator que define quatro métodos de cálculo: adição, subtração, multiplicação e divisão. A anotação @WebService indica que a classe Calculator é um serviço da Web, enquanto a anotação @WebMethod indica que cada método é um endpoint.

A classe CalculatorPublisher é usada para publicar o serviço da Web. A chamada a Endpoint.publish define a URL base do serviço da Web (http://localhost:8080/calculator) e a classe Calculator que fornece os endpoints.

Para executar este código, basta compilá-lo e executar a classe CalculatorPublisher. O servidor SOAP estará disponível na porta 8080, e os endpoints estarão disponíveis em http://localhost:8080/calculator.
