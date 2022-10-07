# Fabric_test-network
Here you find instructions to start your Hyperledger fabric test-network in your linux/ubuntu system.

First Create a folder and navigate to that folder in terminal. Now, download the prereqs-ubuntu.sh file into your local machine.

Now, run the below command to install all the prerequisites in your local machine
```
chmod u+x prereqs-ubuntu.sh
sh prereqs-ubuntu.sh
```

Once all the prerequisites got installed in your local machine, run the below command to download the latest fabric images.
```
curl -sSL https://bit.ly/2ysbOFE | bash -s -- 2.2.3 1.5.2
```

Now, open this particular folder in VSCode. Here you see a folder named fabric-samples.
Copy the test-network folder from fabric-samples folder and past it in the root folder. Now navigate to this folder in your terminal. 

In this folder there is file called network.sh. This file has got all the necessary commands to 
  * Up the network
  * Create a channel
  
To start the network, run the below command
```
./network.sh up
```
This networkup function
 * first check the pre-requisites
 * Create a crypto materials
 * Then start docker network using docker compose file which is already included as a part of this test-network folder.
 
Once, network got sucessfully up and running, Use the below command to create channel called **mychannel** on your network.
```
./network.sh createChannel
```
 
At this point, you have a blockchain network which is sucessfully running with
 * 2 Organizations
 * 2 peers
 * channel named myChannel.
 
You can check your docker container details by running below command in your terminal
``` 
docker ps
```
  
Now, If you have a chaincode, you can install it on your network.
  
To stop and clean the docker containers, run the below command
```
docker rm -f $(docker ps -aq) 
docker volume rm $(docker volume ls)
```

**A big Thank you for following me**:heart:. Kindly share this with your friends who are interested to learn Hyperledger fabric :pray:
