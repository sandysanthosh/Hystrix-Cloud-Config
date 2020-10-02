# Hystrix-Cloud-Config


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
@EnableHstrixDashboard
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

      





<a href="http://starwalt.in/Blogs/index.html">Follow us on Blog</a>
