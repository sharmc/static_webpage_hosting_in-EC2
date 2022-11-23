
# static_webpage_hosting_in-EC2
I am hosting a static webpage using AWS EC2 instance.
1. Launch an EC2 instance.
   >launch EC2 instance, choose default options in AMI(Amazon Linux AMI,instance type, storage, add tag.
   configure security group- keep the ssh rule and allow all traffic in type section.
   Review the configurations and click launch instance.
2. SSH into EC2 instance and install webserver
   >you will see your new instance is running or wait for it to come up and running.
   to login to ec2 instance you need to convert pem file to ppk file by using puttygen and then using putty you can login to the server
   open putty , under session put the hostname (public DNS of instance) and under connect-SSH-auth put the private key file for authentication ( private key will be      ppk file generated via puttygen). you will logged into the server and user the default username.
3. Elevate your privileges and install all the package.
   >sudo su
   yum update -y
4. Install Apache webserver and start it
   >yum install httpd -y
   service httpd start
5. configure webserver to start in case it stops.
   >chkconfig httpd on
6. create HTML file for static webpage
   >cd /var/www/html
   nano index.html
   paste below html code (the code is just to display "1")
   
          <html><body>1</body></html>
       

       
   save nano editor by clicking ctrl+o and ctrl+x
   cat to index.html to see the content
7. got to ec2 instance click on the server and copy the Public IPv4 DNS in new page you will seee the content in the webpage.
8. once done, cleanup the env.

   
