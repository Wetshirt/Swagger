# Swagger

簡單的swagger範例

## 1. maven

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
    
可以到 [http://localhost:8080/v2/api-docs](http://localhost:8080/v2/api-docs) 

> 為什麼是/v2/api-docs? [Spring Reference](https://springfox.github.io/springfox/docs/current/#customizing-the-swagger-endpoints)

上面會顯示JSON格式

## Swagger UI 

Swagge UI 提高可讀性

在 ApiInfo 配置相關設定

訪問 swagger-ui.html [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html) 























