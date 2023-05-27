| NAME | PROMPT | DESCRIPTION | EXAMPLE |
|---|---|---|---|
| Pod | The container used in the Pod has the image NM:v1.0.0, and it listens on port 8000 for HTTP requests. | | [` ./yaml/app.yaml`](./yaml/app.yaml) |
| Liveness Probe | we can determine that this manifest was written to deploy a Pod with a container that has a Liveness Probe to check its health. The Liveness Probe makes an HTTP request to path / on port 8000 at specific intervals and with the parameters set. In addition, the container also listens to port 8080 for HTTP requests | | [`./yaml/app-livenessProbe.yaml`](./yaml/app-livenessProbe.yaml) |
| Readiness Probe | we can determine that this manifest was written to deploy a Pod with a container that has both Liveness Probe and Readiness Probe. The Liveness Probe checks the health of the container by making an HTTP request to path/ on port 8000. Readiness Probe checks the container's readiness by making an HTTP request to the /ready path on the same port | | [`./yaml/app-readinessProbe.yaml`](./yaml/app-readinessProbe.yaml) |
| Volume Mounts | we can determine that this manifest was written to deploy a Pod with a container that has a Liveness Probe and a Readiness Probe to check its health and readiness, respectively. In addition, a "data" volume is used to mount to the "/data" path inside the container, and this volume is of type "hostPath" and mounted to the "/var/lib/app" path on the host node. | | [`./yaml/app-volumeMounts.yaml`](./yaml/app-volumeMounts.yaml) |
| CronJob | we can determine that this manifest was written to create a CronJob that runs a task every 5 minutes. The task executes the echo "Hello world" command in a container with the "bash" image. The restart policy is set to "OnFailure", which means that the Pod will only be restarted if the task fails | | [`./yaml/app-cronjob.yaml`](./yaml/app-cronjob.yaml) |
| Job | we can determine that this manifest was written to create a Job that executes the command gsutil -m rsync -dr gs://glow-sportradar/ /data/input in the container with the image "google/cloud-sdk:275.0.0-alpine". A GCE Persistent Disk with the name "glow-data-disk-200" is used to store data. The restart policy is set to "Never", which means that the Job is executed only once | | [`./yaml/app-job.yaml`](./yaml/app-job.yaml) |
| Multi-container pod | this manifest was written to create a Pod with two containers - the first container contains the Nginx web server and the second container runs a command that infinitely appends the current date to the /html/index.html file. Both containers share a common temporary. | | [`./yaml/app-multicontainer.yaml`](./yaml/app-multicontainer.yaml) |
| Resource Limits | this manifest could be created to deploy a single-container Pod on a Kubernetes cluster with defined requirements and resource constraints | | [`./yaml/app-resources.yaml`](./yaml/app-resources.yaml) |
| Secrets | this manifest could be created to deploy a Pod with a Redis container that derives a confidential username and password from the secret "mysecret1" and uses these values as environment variables in its backend environment. | | [`./yaml/app-secret-env.yaml`](./yaml/app-secret-env.yaml) |
