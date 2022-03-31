==== Image Management

Images are pulled from a registry. A registry can be public or private. 
Podman registries are configured in /etc/containers/registries.conf.
For some registries, you need to login to be able to pull & push images.

podman
        search
        images
        inspect
        save -o
        load -i
        rmi
        rmi --force
        rmi -a
        rmi -a --force
        commit
        tag
        push


==== Container Management

Containers are created from images locally stored on the host

podman
        run
        ps
        ps -a
        top
        stats
        logs
        diff
        stop
        start
        restart
        kill
        pause
        unpause
        exec
        rm
        rm -a
        rm --force
        rm -a --force

                --name
                -d
                -p
                -e
                -i
                -t


mkdir /home/mourad/container-data

echo "<h1>Welcome to my Web container</h1>" > /home/mourad/container-data/index.html

sudo semanage fcontext -a -t container_file_t '/home/mourad/container-data(/.*)?'
sudo restorecon -Rv /home/mourad/container-data

podman unshare chown -R 27:27 /home/mourad/container-data


podman run --name web100 -d -p 8090:80 -v /home/mourad/container-data:/usr/local/apache2/htdocs/ httpd



podman run httpd

podman commit <containerName> <imageName>

podman tag <imageName> docker.io/mouradn81/custom-web

podman push docker.io/mouradn81/custom-web






# This is a comment line 
FROM ubi8/ubi:8.3 
LABEL description="This is a custom httpd container image" 
MAINTAINER NIC 
RUN yum install -y httpd && \
    yum clean all
RUN yum install telnet -y
RUN mkdir /documentation
EXPOSE 80 
ENV LogLevel "info" 
ADD https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/techpaper/performance/vsphere-esxi-vcenter-server-70U3-performance-best-practices.pdf /documentation 
COPY ./src/ /var/www/html/ 
#USER apache 
ENTRYPOINT ["/usr/sbin/httpd"] 
CMD ["-D", "FOREGROUND"] 





apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80



# Create an application from a Docker image

    oc new-app httpd
    oc new-app mysql MYSQL_ROOT_PASSWORD=rootpass -l tier=db --name database1

# Create an application from a specific registry

    oc new-app --image=quay.io/mnakib/web-custom

# Create an application from S2I (Source To Image)

    oc new-app php~https://github.com/mnakib/php-helloworld.git --context-dir=src

    oc start-build php-helloworld
  


  


  oc scale deployment <deplymentName> --replicas=11

 

      
  oc create deployment test-web1 --image=nginx --dry-run -o yaml > test-web1.yaml

  






