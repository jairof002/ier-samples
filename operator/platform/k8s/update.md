# Updating IBM Enterprise Records 5.2.1.3 on Certified Kubernetes

- [Step 1: Modify the software that is installed](update.md#step-1-modify-the-software-that-is-installed)
- [Step 2: Apply the updated custom resources](update.md#step-2-apply-the-updated-custom-resources)
- [Step 3: Verify the updated automation containers](update.md#step-3-verify-the-updated-automation-containers)

## Step 1: Modify the software that is installed

Use the information in the following link to configure the software that is already installed. You can modify the installed software, remove it, or add new components. Use the same custom resources YAML file that you deployed with the operator to make the updates (for example my_ier_v1_ier_cr.yaml).

- [Configure IBM Enterprise Records 5.2.1.3](../../IER/README_config.md)

## Step 2: Apply the updated custom resources

1. Review your custom resources YAML file to make sure it contains all of your intended modifications.

   ```bash
   $ cat descriptors/my_ier_v1_ier_cr.yaml
   ```

2. Run the following commands to deploy the configured components:

   ```bash
   $ kubectl apply -f descriptors/my_ier_v1_ier_cr.yaml
   ```

## Step 3: Verify the updated automation containers

When all of the pods are *Running*, you can access the status of your containers with the following commands.

```bash
$ kubectl status
$ kubectl get deployment
$ kubectl logs <operatorPodName> -f -c operator
```
