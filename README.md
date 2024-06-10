# Todo REST example .NET8
## todo with in memory database


### Get Started

#### Run in your host machine
1. launch with profile http
```
dotnet run --launch-profile http
```
2. open browser `http://localhost:5025/swagger/index.html`



#### Release build 
1. build release with out directory
```
dotnet publish -c Release -o out
```

#### Run with docker
1.build image
```
docker build -t dot8-todo-image -f Dockerfile .
```

2.run image
```
docker run -p 8080:8080 dot8-todo-image
```

\
&nbsp;
\
&nbsp;
\
&nbsp;
\
&nbsp;

learn more [here](https://learn.microsoft.com/en-us/aspnet/core/tutorials/min-web-api?view=aspnetcore-8.0&tabs=visual-studio)