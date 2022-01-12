# Demo 1 - Deploy an App

## Demo Overview
In this demo you'll deploy a front end web server written in golang and a back end mongodb database container .

![architectural diagram](/img/demo1/demo1-diag1.png)

The database container uses ephemeral storage so deleting that container will result in the loss of your data. In a later demo we'll explore persistent volume claims where you can persist that data across container crashes.

## Prerequisite Steps for the Demo

This first demo and all the subsequent demos assume that you have:
- A VMware Cloud on AWS SDDC deployed
- Tanzu Kubernetes Grid Managed Service Activated
- A namespace created with the `vsan-default-storage-policy` added.
- At least one Tanzu Kubernetes Cluster deployed.

## Demo Steps

1. Change your working directory to this demo1 directory.

``` bash
cd demo1-deployAnApp
```

2. Deploy the loyalty namespace

``` bash
kubectl apply -f 1-loyalty-namespace.yaml
```

3. Deploy the mongo database with a preconfigured password and kubernetes service.

``` bash
kubectl apply -f 2-mongo_dep-svc.yaml
```

4. Deploy the front end web server with a kubernetes service of type Load Balancer

``` bash
kubectl apply -f 3-ht-loyalty_dep-svc.yaml
```

5. List the pods running within the loyalty namespace

``` bash
kubectl get pods -n loyalty
```

6. Find the Load Balancer IP Address

``` bash
kubectl get svc -n loyalty
```

![External Load Balancer Diagram](/img/demo1/demo1-extlb.png)


6. View the application in a browser

![App View](/img/demo1/demo1-app.png)

7. NIMBUS ONLY 

If using a nimbus environment you may need to either access the LoadBalancer IP from your jump host, or create a NAT rule to NAT the IP to a public address.

![NAT Rule for Nimbus Lab](/img/demo1/demo1-nat.png)

