# flux-configuration-playground


# Flux is mainly usd for CD like Jenkins

![image](https://user-images.githubusercontent.com/54719289/116299017-13dabc80-a795-11eb-9659-55e343e234ea.png)

Flux is described as a GitOps operator for Kubernetes that synchronises the state of manifests in a Git repository to what is running in a cluster. This tool runs in the cluster, to which updates would be applied, and its main function is watching a remote Git repository to apply changes in Kubernetes manifests


#Flux is a tool that automatically ensures that the state of a cluster matches the config in git. It uses an operator in the cluster to trigger deployments inside Kubernetes, which means you don't need a separate CD tool. It monitors all relevant image repositories, detects new images, triggers deployments and updates the desired running configuration based on that (and a configurable policy).

#The benefits are: you don't need to grant your CI access to the cluster, every change is atomic and transactional, git has your audit log. Each transaction either fails or succeeds cleanly. You're entirely code centric and don't need new infrastructure.


![image](https://user-images.githubusercontent.com/54719289/116298913-f574c100-a794-11eb-9a19-11cdb9b41f32.png)


For example:
===========

Refer below link for installing flx
[Gitops-FluxCD](https://github.com/logambigaik/Gitops-FluxCD)


# Practising with minikube  and python:

  Install minikbe
  [minikube-setup] (https://github.com/logambigaik/minikube-setup.git)
  
# After installing minikube, create namespace

  kubectl create ns python-namespace

![image](https://user-images.githubusercontent.com/54719289/116387952-3e6b5a80-a813-11eb-9619-569df155a354.png)

  
# Run the below commmand to install flux in Git:

              export GHUSER="logambigaik"
              fluxctl install --git-url=git@github.com:${GHUSER}/flux-CD-Gitops  --git-user=${GHUSER}  --git-email=${GHUSER}@users.noreply.github.com --git-branch=main --git-path=Kubernetes --namespace=python-ns | kubectl apply -f -

![image](https://user-images.githubusercontent.com/54719289/116396991-edad2f00-a81d-11eb-8425-b9dd19b09c7c.png)



              kubectl get all -n python-ns

![image](https://user-images.githubusercontent.com/54719289/116397087-0ddcee00-a81e-11eb-8cff-640091173ee1.png)


              kubectl get pods -n python-ns
              
![image](https://user-images.githubusercontent.com/54719289/116397158-277e3580-a81e-11eb-9bd7-68571e8ecda5.png)



# Check the deplyment status with rollout command:

            kubectl -n python-ns rollout status deployment/flux
            
![image](https://user-images.githubusercontent.com/54719289/116397510-9196da80-a81e-11eb-8f4f-56e140b7caa3.png)



          kubectl get deploy -n python-ns
         
![image](https://user-images.githubusercontent.com/54719289/116397619-b9863e00-a81e-11eb-8c7c-3c8cdbd3448e.png)



        fluxctl identity --k8s-fwd-ns flux
        
  ![image](https://user-images.githubusercontent.com/54719289/116398609-e71fb700-a81f-11eb-8237-1659119f13c9.png)


  # to fix the above issue , install socat 
  
          yum install -y socat
          
  ![image](https://user-images.githubusercontent.com/54719289/116398716-04548580-a820-11eb-9f2f-1dd07e1175c9.png)
  
  
  
  # Copy the ssh and update in git Settings -> Repository -> Deploy Keys under flux-CD-Gitops repository
  
  
  ![image](https://user-images.githubusercontent.com/54719289/116399478-e0457400-a820-11eb-8984-dfca3639158a.png)


         





