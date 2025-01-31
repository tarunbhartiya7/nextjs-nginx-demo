how to deploy your nextjs app on nginx with pm2

- docker run -it -p 8080:80 ubuntu
- inside ubunt install git, curl, nvm, pm2, nginx
- go to /var/www and git clone your project here
- npm i
- npm run build
- pm2 start npm --name "nginx-demo-app" -- start
- vim /etc/nginx/sites-enabled/default

```
server {
	listen 80;

	location / {
		include proxy_params;
		proxy_pass http://localhost:3000;
	}
}
```

- start nginx with `nginx`
- check nginx configuration is correct with `nginx -t`
- start with `nginx -s reload`
- `nginx -s stop`
- `pm2 stop all`
- `pm2 ls`
