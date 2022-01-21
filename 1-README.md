# Team Members:

- Mohamad Kassem
- Arjun Puliyasseri

# To Run The Project:

1- Create: IAM user group, EC2 instance, S3 bucket and 2 Fifo queues.

2- Run the Worker code as Maven Build to generate a Jar file.

3- Connect to your EC2 instance (using SSH or any other method). Then enter your credentials.

4- Upload the Jar file to your EC2 instance using SFTP (Use suitable method according to your OS, for me I used Putty and fileZilla on my Windows machine).

5- Now it is time to run our worker jar file on our EC2 instance.

6- Run Client.java Locally.

After finishing all these steps, the simulation will be running (Client locally and Worker on the EC2 Server).
The Client will send a request, the Worker will satisfy it and generate a file containing the results, (which the Client will download).
At the end when the request is satisfied and the Client downloads his resultFile.txt, we empty the queues to open the door for new client(s) requests to the server.
And at this point the Client will terminate, while the Worker keep waiting for a new request (forever) until we choose to terminate it manually.

