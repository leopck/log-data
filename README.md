# log-data
Just a simple python script with php to store my dynamic IP of my server into another server.

Technically, possible to use a ddns to solve this issue however, I wanted to attempt solving this without using external softwares and wanted just a simple logging system also, this solution is also applicable to private network and not only public network. Therefore, static IP of your server is not needed since it'll update the server on it's IP address via the logs.

The way this works is pretty simple, inside the client server that has the dynamic IP, contains a python script that will get it's own IP address and send a HTTP GET request along with it's IP address.
The host server will receive the HTTP GET request via PHP and will write into a directory/file called "log_data_dir/ddns.txt".

Example inside the "log_data_dir/ddns.txt":

    10.101.100.10

More updates to come....
