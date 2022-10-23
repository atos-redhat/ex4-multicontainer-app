# Ex. 4. Multicontainer application

This application is based on Postgres as a Database and Spring Boot application running on a WildFly image

## Steps to do

1. Clone the repository to your local machine.

2. Deploy the postgres database using `oc apply` command using resources specified in `postgres.yaml`. Use `--help` parameter to see how to apply changes from a file.

3. Check if the pod with postgres database is running.

4. Import a `wildfly`image by running
    ```bash
    oc import-image wildfly --confirm --from quay.io/wildfly/wildfly-centos7
    ```
    
5. The imported image should be visible after running
    ```bash
    oc get is
    ```

6. Deploy the Spring Boot application by running `oc new-app` command, with name `parkin` using image stream `wildfly` and the source code, located at https://github.com/rhoctraining/parkin.git.

7. Check of the pod with the application is running. Additionally, check the logs of the pod for possible errors.

8. Create a route for the application by running
    ```bash
    oc expose service parkin
    ```
    
9. Find the parkin deployment in the OpenShift UI console and open the link, the main page of the application should be visible.


## Useful commands
 * `oc get pods`
 * `oc get all`
 * `oc apply` with a file parameter
 * `oc new-app --help`
 * `oc get is`
 * `oc expose service <service_name>`
 
