# CEG3120 - Course Work

## Building the Web Service Container

### Website Content
The website content in contained in web-content/. When loaded it defaults to index.html.
The content of this website is a demonstation of the different html elements. I has some fun facts about me and a few diffrent lists. It was made in my Web Development Class. If changing the content, replace all files in Web-content with your intended website content.

Link to WebContent [web-content](web-content)
### Dockerfile
The `Dockerfile` has just two instructions.
```dockerfile
FROM httpd:2.4
COPY ./web-content/ /usr/local/apache2/htdocs/
```

- The `FROM httpd:2.4` Starts the container from the Appache HTTP Server image version 2.4.
- `COPY ./web-content/ /usr/local/apache2/htdocs/` this copys the contents of `web-content` into the apache servers default document root.

The `Dockerfile` is here: AWS-LB\Dockerfile [Dockerfile](Dockerfile)

docker image here: https://hub.docker.com/r/blockofcheese/my-apache2
#### Building the Dockerfile Yourself (localy)

1. First create a web-content folder and put your website contents inside. And aquire the Dockerfile linked above
2. While being in the folder that houses the web-content folder and Dockerfile. fun the following command: `docker build -t <InsertYourDockerHubUsername>/my-apache2:v1 .`
3. This should create a Docker image that includes the apache server software and your web-contents. 
4. Then login to your docker by running `docker login -u <UserName>`. It will ask you for your Person access Token, If you do not have it floow the instructions below this.
5. Then run `docker push <InsertYourDockerHubUsername>/my-apache2:v1`
6. This will push your docker image to your dockerhub account.

#### Creating a Personal Access Token
1. Sign into `hub.docker.com`.
2. Open account setting, then Personal Access tokens and click Generate New Token
3. Add a description of your choosing
4. Set the permisions of this Token, For me i have the, at Read and Write. 
5. Click Generate and copy the token to a safe place, it will not be shown again.

