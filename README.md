# Tutorial 10 Deployment
Farrel Ayman Abisatyo  <br>
2206828916 <br>
Advanced Programming B <br>

## Reflection 1
### 1. Compare the application logs before and after you exposed it as a Service.

<img src= "assets/images/Screen Shot 2024-05-17 at 01.06.22.png" width="750px"> <br>

Yes, there is a difference. After the service is exposed, it can receive requests, and the logs will record these incoming requests. As show in the picture, if the hello-node service is refreshed multiple times, the logs will show entries corresponding to each request made to the service. In this instance its request with GET method.

### 2. Notice that there are two versions of kubectl get invocation during this tutorial section. The first does not have any option, while the latter has -n option with value set to kube-system.

The difference between the two kubectl get commands lies in the -n option. Using -n specifies that the command should target a particular namespace. This is important when there are multiple services with the same name across different namespaces. By using the -n option, we can narrow down the search to the specified namespace provided after the -n flag.

## Reflection 2
### 1. What is the difference between Rolling Update and Recreate deployment strategy?
> Hint: Read the Deployments documentation.

Rolling Update:

- It updates the application gradually by replacing the old versions of the application with new ones, one at a time.
- It ensures that theres no downtime as the new version is introduced incrementally, maintaining a mix of old and new versions until the update is complete.
- Ideal for scenarios where maintaining service availability is crucial during updates.<br>

Recreate:

- the process shuts down all old versions of the application before bringing up the new versions.
- In terms of availability it cause downtime because the old version is completely stopped before the new version starts.
- It is suitable for applicatios where downtime is acceptable or where the old and new versions cannot coexist.

### 2. Try deploying the Spring Petclinic REST using Recreate deployment strategy and document your attempt.

<img src= "assets/images/Screen Shot 2024-05-17 at 18.38.24.png" width="750px"> <br>
<img src= "assets/images/Screen Shot 2024-05-17 at 18.38.33.png" width="750px"> <br>
<img src= "assets/images/Screen Shot 2024-05-17 at 18.39.41.png" width="750px"> <br>

### 3. Try deploying the Spring Petclinic REST using Recreate deployment strategy and document your attempt.
I created this 'recreate' version of deployment file by editing deployment strategy from rolling update to recreate

### 4. . What do you think are the benefits of using Kubernetes manifest files? Recall your experience in deploying the app manually and compare it to your experience when deploying the same app by applying the manifest files (i.e., invoking `kubectl apply -f` command) to the cluster.
The main advantage of using manifest files is efficiency because we dont need to remember the specific procedures and syntax for updates or deployments anymore. It's kind of like importing a document; we don't need to know the steps taken to create it, we just have a ready-to-use file. This also reduces the possibility of human error because the service created will match the contents of the manifest file, eliminating the risk of mistakes when typing syntax manually.