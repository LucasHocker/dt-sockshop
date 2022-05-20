# dt-sockshop
Fork of WeaveWorks' Sockshop demo application with minor changes for Dynatrace demoability

To deploy:
1. Create & connect to a minspec K8s cluster (any flavor). AWS/Azure/GCP all offer limited credits to individuals that are suitable for demo purposes.
2. Confirm you have `kubectl` access. `kubectl get nodes` should return at least one node.
3. Run deploy script: `cd utils; ./deploy-sockshop.sh`
4. Confirm deployment successful: `kubectl get -n dev all` and `kubectl get -n production all`
5. Connect to demo application: `kubectl get -n production service front-end` and connect to the external-ip:port in your browser

When done, be sure to spin resources back down:
1. Remove sockshop: `cd utils; ./delete-sockshop.sh`
2. Stop or delete your K8s cluster
