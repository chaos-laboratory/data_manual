# Register New Deployment

## Particle Web IDE
1. Go to the Particle [Web IDE](build.particle.io) and login with our CHAOS Lab credentials. Approach our lab memeber for the logins. In the Web IDE, go to Code -> Search for STAPI -> STAPI03_RegisterNewDeployment.
    ```{figure} /_static/043new_deploy/new_deploy.png
    :width: 100%
    :name: new_deploy

    Register a new deployment of an already registered Particle Device.
    ```
    a. The parameters are similar to registering a new Particle Device. Refer to Step 11a. of the example: ({doc}`../020/021work_eg1`) for details of each parameter. Just make sure that the 'thingDESC' parameter is unique for the script to work.

    b. Flash the code to the Particle Device. The event page of the Particle Device will show this message if successfully registered.
    ```{figure} /_static/043new_deploy/new_deploy2.png
    :width: 100%
    :name: new_deploy2

    Successful registration of a new deployment of a Thing.
    ```
    c. Go to [https://andlchaos300l.princeton.edu:8080/FROST-Server/v1.0/Things](https://andlchaos300l.princeton.edu:8080/FROST-Server/v1.0/Things) to get the details of the new deployment. Use Firefox for the best viewing result. Take not of the ID and the datastream ID as that is what will be specified when posting data to the database.

    ```{figure} /_static/043new_deploy/new_deploy3.png
    :width: 100%
    :name: new_deploy3

    Details of the registered new deployment of a Thing.
    ```
