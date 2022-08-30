# cloud-deploy-demo

Create Dev and Prod Clusters 
```
gcloud container clusters create-auto ccd-dev  --project=demoneil --region=us-central1 && gcloud container clusters create-auto ccd-prod --project=demoneil --region=us-central1
```


Create pipiline
```
gcloud deploy apply --file clouddeploy.yaml --region=us-central1 --project=demoneil
```

Create a Release 
```
gcloud deploy releases create test-release-013   --project=demoneil   --region=us-central1   --delivery-pipeline=simple-node-app   --images=my-app-image=gcr.io/demoneil/github.com/neilghosh/simple-node-service:ea54e77cb158f4806852dba395767a009d4e777a
```

https://kubernetes.io/docs/tasks/access-application-cluster/service-access-application-cluster/
```
//get the node port from service describe
kubectl get nodes --output wide //get the node ip
gcloud compute firewall-rules create test-node-port1  --allow tcp:31014
```