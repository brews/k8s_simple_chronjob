# k8s_simple_cronjob
Example of a simple Kubernetes scheduled job (cronjob) pattern.

## Toy deployment

Begin by creating the cronjob object (`kubectl create -f cronjob.yaml` - assuming you're connected to a cluster or local minikube).

Once it deploys you can see info on it with `kubectl describe cronjob`. This gives information on its runs so try this command again after the job has had time to run once.

After it has run its job once you can see the job’s pod (via `kubectl pods`) and then check its log with `kubectl logs <cronjob-pod-here>` and you should see the message the container prints (“simplescript.py is running” with a little logging information -- some award winning writing there).

Note. For the moment, you’ll need to kill the pod/cronjob manually - e.g. via `kubectl delete -f cronjob.yaml` - sorry. By default (at the time of writing) pods from the last three jobs will be retained. Failed job runs will be retried.
