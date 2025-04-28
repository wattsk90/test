### I've tried a number of container configurations, but everything results in one of the following 2 errors.

* Timed out while attempting to establish a connection to the container. You can increase this timeout by setting the SAM_CLI_CONTAINER_CONNECTION_TIMEOUT environment variable. The current timeout is 20.0 (seconds).

* Error: .NET binaries for Lambda function are not correctly installed in the /var/task directory of the image when the image was built. The /var/task directory is missing.


~~~
cd MyLambdaShizz

export PATH="$PATH:$HOME/.dotnet/tools/"

sam build

#results in 1st error
sam local invoke

#results in 2nd error (after it starts and trying to hit it)
sam local start-api --warm-containers EAGER --host 0.0.0.0 --container-host host.docker.internal
~~~