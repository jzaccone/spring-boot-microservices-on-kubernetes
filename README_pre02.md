
# Lab Environment Setup

Every time when you start a new terminal/command window, steps in the section must be performed to setup a new environment.

Run these steps inside the console-in-a-browser environment provided by your instructor, or in a terminal/command window on your local machine.

1. Open a new terminal ort command window.

1. Login to the IBM Cloud. If prompted, enter user name and password. 

    ```sh
    ibmcloud login
    ```

1. List the clusters and locate the cluster corresponding to the userId you used to login to the console-in-a-browser environment. For example, if you are user028, your cluster will be user028-cluster.

    ```sh
    ibmcloud ks clusters
    ```
    Your Lite cluster should show up on the list. The cluster name should be in the format of `user###-cluster`, for example `user003-cluster`.

1. Configure your Kubernetes client using this command. This will also configure your Kubernetes client for future login sessions by adding the command into your .bash_profile. 

    ```sh
    eval $(ibmcloud ks cluster-config --cluster <your k8s cluster> --export | tee -a ~/.bash_profile) 
    ```
    >If the command has a syntax error in your terminal (e.g. windows cmd shell), you may instead run the command `ibmcloud ks cluster-config --cluster <your user>-cluster`. Then, copy the output and execute it in the same terminal.

1. You should be able to use kubectl to list kubernetes resources. Try getting the list of pods (there should be none yet)

    ```sh
    kubectl get pods
    No resources found.
    ```

1. Login to the registry service

    ```sh
    ibmcloud cr login
    ```






