# nginx-autoindex

This container takes the official alpine nginx image and turns on the autoindex option.

You can do a simple mount to simply serve files from your local
file system with nginx.  Make sure to map the directory you want to serve from with the
`-v` command

```bash
docker run -d --name nginx-autoindex --restart unless-stopped -p '80:80' -v /home/my-user/html:/usr/share/nginx/html:ro painteau/nginx-autoindex
```

Then navigate in a browser to http://127.0.0.1 and view the files in the directory you mounted in your volume
