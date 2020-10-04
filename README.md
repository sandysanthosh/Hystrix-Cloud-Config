# Hystrix-Cloud-Config


    * Fault Tolerancee
    * Circuit Breaker

#### In Gateway:

```
pom.xml:

    Spring-Cloud-Starter-netflix-hystrix

```
#### In application.yml:

```
filters:
  -name : circuitbreaker
  -args : 
      name :  Payment-service
      fallback : forward:/payment-fallback
 
 filters:
  -name : circuitbreaker
  -args : 
      name :  Order-service
      fallback : forward:/order-fallback
  
    
```

#### Pom.xml:

```
<dependency>
<groupId>org.springframework.cloud</groupId>
<artifactId>spring-cloud-starter-netflix-hystrix</artifactId>
</dependency>

<dependency>
<groupId>com.netflix.hystrix</groupId>
<artifactId>hystrix-dashboard</artifactId>
<version>1.5.18</version>
</dependency>
    
```

#### Annotations:

```
@EnableHstrixDashboard
@EnableHystrix
@SpringBootApplication
```

#### RestController.java:

```
@HystrixCommand(fallbackMethod="sendErrorResponse")
@RequestMapping(Value="/produts" , method=RequestMethod.POST)
Coupon cou = Coupon.getCoupon(product.getDiscount());
product.setPrice(product.getPrice().subtract(coupon.getDiscount));
return repo.save(product);
}

public Product sendErrorRespose(Product Product){
return Product;
}
```

#### EnableHystrixDashboard:

```
@EnableHstrixDashboard
@EnableHystrix
@SpringBootApplication
```   

#### Application.Properties:

```
server.port = 9195
```

#### To Test:

```
localhost:8989/actuator/hystrix.stream

localhost:9195/hystrix
```




<a href="http://starwalt.in/Blogs/index.html">Follow us on Blog</a>
