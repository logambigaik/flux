# flux-configuration-playground


# Flux is mainly usd for CD like Jenkins

![image](https://user-images.githubusercontent.com/54719289/116299017-13dabc80-a795-11eb-9659-55e343e234ea.png)

Flux is described as a GitOps operator for Kubernetes that synchronises the state of manifests in a Git repository to what is running in a cluster. This tool runs in the cluster, to which updates would be applied, and its main function is watching a remote Git repository to apply changes in Kubernetes manifests


#Flux is a tool that automatically ensures that the state of a cluster matches the config in git. It uses an operator in the cluster to trigger deployments inside Kubernetes, which means you don't need a separate CD tool. It monitors all relevant image repositories, detects new images, triggers deployments and updates the desired running configuration based on that (and a configurable policy).

#The benefits are: you don't need to grant your CI access to the cluster, every change is atomic and transactional, git has your audit log. Each transaction either fails or succeeds cleanly. You're entirely code centric and don't need new infrastructure.


![image](https://user-images.githubusercontent.com/54719289/116298913-f574c100-a794-11eb-9a19-11cdb9b41f32.png)


For example:
===========

Refer below link
[Gitops-FluxCD](https://github.com/logambigaik/Gitops-FluxCD)


