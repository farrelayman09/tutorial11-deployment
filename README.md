# Tutorial 10 Deployment
Farrel Ayman Abisatyo  <br>
2206828916 <br>
Advanced Programming B <br>

## Reflection
### 1. Compare the application logs before and after you exposed it as a Service.

<img src= "assets/images/Screen Shot 2024-05-17 at 01.06.22.png" width="750px"> <br>

Yes, there is a difference. After the service is exposed, it can receive requests, and the logs will record these incoming requests. As show in the picture, if the hello-node service is refreshed multiple times, the logs will show entries corresponding to each request made to the service. In this instance its request with GET method.

### 2. Notice that there are two versions of kubectl get invocation during this tutorial section. The first does not have any option, while the latter has -n option with value set to kube-system.

The difference between the two kubectl get commands lies in the -n option. Using -n specifies that the command should target a particular namespace. This is important when there are multiple services with the same name across different namespaces. By using the -n option, we can narrow down the search to the specified namespace provided after the -n flag.