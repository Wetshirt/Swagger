# Swagger

一個簡單的swagger範例

使用spring boot && maven 

## 1. 先在maven把相關的jar抓進來

    <!--  Swagger  -->
    <dependency>
        <groupId>io.springfox</groupId>
        <artifactId>springfox-swagger2</artifactId>
        <version>2.9.2</version>
    </dependency>
    
    <!--  Swagger UI  -->
    <dependency>
        <groupId>io.springfox</groupId>
        <artifactId>springfox-swagger-ui</artifactId>
        <version>2.9.2</version>
    </dependency>

[pom.xml](https://github.com/Wetshirt/Swagger/blob/master/pom.xml) 
    

## 2. 撰寫 Swagger config檔案

    @Configuration      //告訴spring boot 這是configuration類別
    @EnableSwagger2     //啟用Swagger
    public class SwaggerConfig {
        //配置swagger 成功的話可以在 v2/api-docs/ 看到json
        @Bean
        public Docket createRestApi() {
        
            return new Docket(DocumentationType.SWAGGER_2)
                    .apiInfo(apiInfo())     //配置swagger ui
                    .select()
                    .apis(RequestHandlerSelectors.basePackage("com.example.demo.controller"))   //要掃描的controller package在的位置
                    .paths(PathSelectors.any())
                    .build();
        }
        //以下是配製swagger ui
        private ApiInfo apiInfo() {
            return new ApiInfoBuilder()
                    .title("我是標題")
                    .description("我是敘述")
                    .version("1.0")
                    .build();
        }
    }
    
    
[SwaggerConfig.java](https://github.com/Wetshirt/Swagger/edit/master/src/main/java/com/example/demo/SwaggerConfig.java)

> SwaggerConfig.java 要放在spring boot 掃的到的地方(放在applocation同package或是子package)


配置好Docket後就完成swagger了，可以到 [http://localhost:8080/v2/api-docs](http://localhost:8080/v2/api-docs) 

> 為什麼是/v2/api-docs? [Spring Reference](https://springfox.github.io/springfox/docs/current/#customizing-the-swagger-endpoints)

上面會顯示JSON格式的文件(不知道要幹嘛，給前端看...?)

## Swagger UI 

上面那個JSON是有看沒有懂，所以用 Swagge UI 提高可讀性

在 ApiInfo 配置相關設定

到這裡可以訪問 swagger-ui.html [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html) 























