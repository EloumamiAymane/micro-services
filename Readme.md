<h1 style="color: peru">
MicroServices Demo
</h1>
<h5 style="color: #cdbc3f">Steps to create this microservice architecture:</h5>
<ul>
<li>Create Register Service in our demo Eureka discovery</li>
<li>Create Gateway Service to dispatch the incoming requests</li>
<li>Create Customer Service to manage customers</li>
<li>Create Inventory Service to manage products</li>
<li>Create Billing Service to manage bills
<ul>
<li>Create Open Feign Interface to interact with other microservices</li>
</ul>
</li>
</ul>

1. **Create Discovery Service**
<p>In application.properties file we added some configuration to set up our eureka  register.</p>
<img  src="ScreenShot/discoveryServiceConf.png" alt="config file"/>
<p>and then when we run our microservice and access to it by the port 8761 we display eureka discovery interface like below.</p>
<img  src="ScreenShot/eureka-interface.png" alt="eureka-interface"/>

2. **Create Gateway Service**
<p>First Thing we added a config file (application.yml) which we added some config.</p>
<img  src="ScreenShot/gateway-config.png" alt="config file"/>
<p>Like you see we added the port of this microservice,and also the application name,and for the latest property is related to register this microservice to eureka discovery register. </p>
<p>For commented area relates to static routing but we removed it because we switched to dynamic routing. </p>
<img  src="ScreenShot/SetUp-Routing.png" alt="config file"/>
<span>This how we apply dynamic routing programmatically.</span>

3. **Create Customer Service**
<ul>Steps to create this micros.
<li>1. create Customer Entity.
<img src="ScreenShot/Customer-Entity.png">
</li>
<li>2. create Customer Repository.
<img src="ScreenShot/customer-repo.png"></li>
<li>3. Added application.properties file to register this micros to eureka discovery and also the database infos.
<img src="ScreenShot/customer-config.png"></li>
<li>4. Display result which we contact the gateway and then the gateway dispatch this request to the correct micros.
<img src="ScreenShot/customers-result.png">
</li>
</ul>

3. **Create Inventory Service**
<ul>Steps to create this micros.
<li>1. create Product Entity.
<img src="ScreenShot/Product-entity.png">
</li>
<li>2. create Product Repository.
<img src="ScreenShot/product-repo.png"></li>
<li>3. Added application.properties file to register this micros to eureka discovery and also the database infos.
<img src="ScreenShot/product-config.png"></li>
<li>4. Display result which we contact the gateway and then the gateway dispatch this request to the correct micros.
<img src="ScreenShot/product-result.png">
</li>
</ul>

3. **Create Billing Service**
<ul>Steps to create this micros.
<li>1. create Bill & ProductItem Entity.
<img src="ScreenShot/bill-entity.png">
<img src="ScreenShot/ProductItem-entity.png">
</li>
<li>2. create Customer & Product Model to dispaly details data which we retrieved from other micros.
<img src="ScreenShot/Customer-model.png">
<img src="ScreenShot/Product-model.png">
</li>
<li>3. create BillRepo & ProductItem Repo.
<img src="ScreenShot/bill-repo.png">
</li>
<li>4. Added application.properties file to register this micros to eureka discovery and also the database infos.
<img src="ScreenShot/bill-config.png">
</li>
<li>5. added CustomerRestClient & ProductRestClient using openFeign framework for contacting other micros to retrieve the date reside in this micros .
<img src="ScreenShot/customer-rest-client.png">
<img src="ScreenShot/product-rest-client.png">
</li>
<li>6. Create Billing rest controller to fetch bill info.
<img src="ScreenShot/rest-cont.png">
</li>
<li>7. Display result which we contact the gateway and then the gateway dispatch this request to the correct micros.
<img src="ScreenShot/bill-result.png">
</li>
</ul>
