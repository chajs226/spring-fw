# spring-fw
spring framework 기본 셋팅


브라우저에 주소를 입력하면 html 페이지에 연결되도록 하고 싶다.
WARN : org.springframework.web.servlet.PageNotFound - No mapping found for HTTP request with URI 에러
->
Folder structure:

 WEB-INF
       `-static
              |-html
                    `-home.html
              |-css
              `-img

			  
Controller method:

 @RequestMapping(value = "/home")
 public String goHome() { 
      System.out.println("lolololololol");
      return "static/html/home";
 }

 
Spring config:

 <resources mapping="/static/**" location="/WEB-INF/static/" />

 <beans:bean
    class="org.springframework.web.servlet.view.InternalResourceViewResolver">
      <beans:property name="prefix" value="" />
      <beans:property name="suffix" value=".html" />
 </beans:bean>
출처 : https://stackoverflow.com/questions/24980839/spring-mvc-viewresolver-not-mapping-to-html-files
