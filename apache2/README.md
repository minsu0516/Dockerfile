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

# 윈도우기반의 이클립스 에서 셀 스크립터 작성시 
	Eclipse > Help > Install New software...
	
	Name: ShellEd
	Location: http://sourceforge.net/projects/shelled/files/shelled/update/

	 ^M 삭제  