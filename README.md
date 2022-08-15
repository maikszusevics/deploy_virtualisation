# Deployment using nodejs
- Time boxing - 1 day

- What are the dependencies

- Which version of app/nodejs - NodeJs 6.4 or above

- Which environment can this be deployed - Linux ubuntu 16.04 or above

Nodejs is a backend tool used to run javascript. It runs on port 3000

- 3 pages 1 sparta app page 2 fibonacii replacement 3 192.168.10.100:3000/posts for mongodb
- mongodb default port is 27017 and Mongodb allows you to access - mongod.conf you need to allow the required ip
- what is nodejs - how to launch it
- what are the dependencies - install nodejs -> required version of that version 6.0 or above
- sudo apt-get install nodejs -y centOS yum install nodejs -y
- Which env is needed in order for us to deploy this app
- linux ubuntu 16.04 or above

We have extracted the application into the folder with the vagrantfile.

We also installed bundler and made sure it is working by running:
![image](https://user-images.githubusercontent.com/110176257/184634233-7635af48-d6bd-4a23-ae57-ff948d5ddfe4.png)



Then in the vagrantfile we have added a line of code to sync the new app folder with our VM.

```ruby 
#vagrant

Vagrant.configure("2") do |config|



 config.vm.box = "ubuntu/xenial64" # Linux - ubuntu 16.04

# creating a virtual machine ubuntu 
config.vm.network "private_network", ip:"192.168.10.100"
#once you added private network, need to reboot vm

# lets sync our app folder from localhost to vm
config.vm.synced_folder ".", "/home/vagrant/app"
# sync data from localhost 

 
end
```

After adding this code:
- save vagrantfile
- vagrant reload 
- ls should show app folder:
![image](https://user-images.githubusercontent.com/110176257/184627719-568112d1-e9c2-4bc3-afa8-b30e6bbccc66.png)

- cd app, then pwd confirms we are inside the app folder on our virtual machine:
![image](https://user-images.githubusercontent.com/110176257/184627791-8457ffb6-2320-4a99-996b-d2b2f5b15ea3.png)



