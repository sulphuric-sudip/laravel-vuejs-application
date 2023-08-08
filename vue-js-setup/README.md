I have used a simple vue.js application that prints "HELLO WORLD" on the web.  
The source code is inside the [vue-js-app](vue-js-app) folder.

In real practice, Vue.js apps are deployed using the Nginx server for security and other purposes.

[Dockerfile](Dockerfile) contains 2-stage: build stage and production stage.  
Build stage builds the Vue.js application and the production stage uses Nginx to deploy the built app.  
The application created in the build stage(`/app/dist/`) is passed to the Nginx home folder in the production stage.

**Build the image**  
`docker build -t vuejs-app .`

**Run the image**  
`docker run -it -p 8080:80 --rm vuejs-app`
