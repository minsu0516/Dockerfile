#Apache2 
   
	mod_proxy
	proxy_http
	proxy_ajp
	proxy_balancer
	rewrite
	headers

#Volume

	/opt/apache2/www 
	/opt/apache2/conf  


#실행 예시 

```docker run -d -p 80:80 --link tomcat:tomcat  --name myProject company/project-name:version```



#프록시 설정  

 proxy.conf 

	ProxyPass / http://tomcat9/

