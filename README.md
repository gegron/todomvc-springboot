# todomvc-springboot

## Run on GCE

tutorial is available here :
https://docs.google.com/document/d/1ZH1_a4hZ5DrVK5at9KvpjKBLV6Wp6BXrtuKkv3Kqm0g/pub


To start install git and clone the current project
 
```bash
 sudo apt-get install -y git
 git clone https://github.com/jbclaramonte/todomvc-springboot.git
```
 
Execute the shell script which will installs everything you need:
```bash
./install-gce.sh
```

Once everything installed : 

```bash
cd ~/todomvc-springboot

# you may need to run this command first so that your shell knows about the freshly installed spring cli
source "$HOME/.sdkman/bin/sdkman-init.sh"

# and then
# run todomvc app:
spring run **/*.groovy -- --spring.redis.host=<redis ip here>
```


## Run locally
You should have the Spring cli, you can install it easily

```bash
# get the "Software Development Kit Manager" (sdkman) to install the cli
curl -s http://get.sdkman.io | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"

# install springboot cli using sdkman
sdk install springboot
```

You should also have npm installed to install all the js dependency needed for the angularjs app

```bash
cd ~/todomvc-springboot/static
npm install
```

Once done you can run an instance of redis using docker:

```bash
docker run --name redis -d -p 6379:6379 redis
```

Finally run the todomvc app:

```bash
spring run **/*.groovy -- --spring.redis.host=<redis ip here>
```

Open http://localhost:8080

You can also test the api using swagger with http://localhost:8080/swagger-ui.html 



