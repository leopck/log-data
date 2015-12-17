# log-data
Just a simple python script with php to store my dynamic IP of my server into another server.

Technically, possible to use a ddns to solve this issue however, I wanted to attempt solving this without using external softwares and wanted just a simple logging system also, this solution is also applicable to private network and not only public network. Therefore, static IP of your server is not needed since it'll update the server on it's IP address via the logs.

The way this works is pretty simple, inside the client server that has the dynamic IP, contains a python script that will get it's own IP address and send a HTTP GET request along with it's IP address.
The host server will receive the HTTP GET request via PHP and will write into a directory/file called "log_data_dir/ddns.txt".

Example inside the "log_data_dir/ddns.txt":

    10.101.100.10

Step 1: git clone

Step 2: Place php files into the host server and provide permissions

Download and install apache with php5 then place the php files into "/var/www/html/"

Provide permission to the folder
     sudo chown -R www-data:www-data /var/www/html
     sudo chmod -R a+wr /var/www/html
    
Step 3: Place python files into the client server and create a crontab/scheduled task to send the ip address every 24 hours.

Copy your python file "get_ip.py" into any directory, in this case "/home/user/myDir/get_ip.py"

Create a crontab schedule for the python script to run every morning at 6.08am to update it's ip address into the ddns.txt

    crontab -e
    
    ##Add this line to the bottom of the page###
    08 06 * * * python /home/user/myDir/get_ip.py 

More updates to come....
