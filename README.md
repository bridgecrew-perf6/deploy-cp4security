# Deploy IBM Cloud Pak for Security using Ansible

IBM Cloud Pak® for Security (CP4Security) provides a platform to quickly integrate security tools and generate deeper insights into threats across hybrid, multicloud environments. You can find more information at in [CP4Security Knowledge Center](https://www.ibm.com/docs/en/cloud-paks/cp-security/1.9). 

This repository provides Ansible-way to deploy CP4Security on an existing OpenShift Cluster. 

### 1. Pre-requisites
Please ensure that the following pre-requisites are met before executing the ansible scripts to deploy CP4Security.

1. You need an ansible-controller machine from which the scripts are executed. This could be your laptop or a dedicated linux machine. This can only be a Mac or Linux machine and NOT Windows.
2. Install Python 3.10+ on the ansible-controller. Check the version with 'python --version'.
3. Install Ansible 2.12+ on the ansible-controller.Check the version with 'ansible --version'.
4. Ensure that the Python used by Ansible matches with the Python version on the ansible-controller.
5. Check the OpenShift sizing required for CP4Security in the knowledge center Setup OpenShift and ensure that it is reachable from ansible-controller.
6. Install 'oc' (OpenShift CLI) client on ansible-controller.
7. Login into OpenShift cluster using 'oc login' from the ansible-controller.
8. Install the kubernetes core collection for Ansible by running 'ansible-galaxy collection install kubernetes.core'.

**Notes**:
1. The scripts are tested with Python 3.10.1 and Ansible 2.12.1 on MacOS.
2. The scripts are work-in-progress and updated frequently.
3. The script is meant for setup of sandbox environment only on IBM ROKS (OpenShift on IBM Cloud) and not for production.


### 2. Run the scripts to deploy CP4Security

You need to clone the repository on ansible-controller machine. 

Open 'deploy-cp4s.yml' file and enter the right value for the variable 'ENTITLED_REGISTRY_PWD' and save the file (replace the 'put-your-entitlement-key-here' string with your key). You can obtain this key from [MyIBM Container Software Library](https://myibm.ibm.com/products-services/containerlibrary).

Run the following command to run the ansible script, which deploys CP4Security. 

```
ansible-playbook deploy-cp4s.yml
```
It would take about 90 minutes for the installation to complete. 

