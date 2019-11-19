# Start Gitlab server using docker-compose.

## Description:
This task is for run gitlab in the basic configuration. We will use a previously prepared repository.
Before you run docker-compose command you need to clone repository on your station. You have several ways
to arrange this.

If you know your personal token you should type:

git clone https://[your IBM github ID]:[your IBM github Token]@github.ibm.com/SYSP-EDU/gitlab.git

`Be aware!`</br>
Please adjust command settings for your needs. You should use your user and personal token value.

When repo will be on your station go to the `gitlab` directory and type:

`docker-copose up -d`

You should get similar output:

```
Creating network "gitlab_EDU_GITLAB_Net" with driver "bridge"
Creating cicd-gitlab ... done
```

Check if cicd-gitlab container is up:

`docker-compose ps`

Then you should get:

```
Name           Command               State                                            Ports                                  
--------------------------------------------------------------------------------------------------------------------------------
cicd-gitlab   /assets/wrapper   Up (health: starting)   22/tcp, 0.0.0.0:443->443/tcp, 0.0.0.0:4567->4567/tcp, 0.0.0.0:80->80/tcp
```

After 5 mins your container should be started as follow:

```
Name           Command          State                                        Ports                                  
-----------------------------------------------------------------------------------------------------------------------
cicd-gitlab   /assets/wrapper   Up (healthy)   22/tcp, 0.0.0.0:443->443/tcp, 0.0.0.0:4567->4567/tcp, 0.0.0.0:80->80/tcp

```

If for some reason did not started please check logs using command:

`docker logs -f cicd-gitlab`

```
- execute cat /etc/sysctl.conf /etc/sysctl.d/*.conf  | sysctl -e -p -
 * file[delete /etc/sysctl.d/90-postgresql.conf kernel.sem] action delete (skipped due to only_if)
 * file[delete /etc/sysctl.d/90-unicorn.conf kernel.sem] action delete (skipped due to only_if)
 * file[delete /opt/gitlab/embedded/etc/90-omnibus-gitlab.conf kernel.sem] action delete (skipped due to only_if)
 * file[delete /etc/sysctl.d/90-omnibus-gitlab.conf kernel.sem] action delete (skipped due to only_if)
 * execute[load sysctl conf kernel.sem] action nothing (skipped due to action :nothing)

* execute[/opt/gitlab/embedded/bin/initdb -D /var/opt/gitlab/postgresql/data -E UTF8] action run
 [execute] The files belonging to this database system will be owned by user "gitlab-psql".
           This user must also own the server process.

           The database cluster will be initialized with locale "C.UTF-8".
           The default text search configuration will be set to "english".

           Data page checksums are disabled.

           fixing permissions on existing directory /var/opt/gitlab/postgresql/data ... ok
           creating subdirectories ... ok
           selecting default max_connections ... 100
           selecting default shared_buffers ... 128MB
           selecting dynamic shared memory implementation ... posix
           creating configuration files ... ok
           running bootstrap script ... ok
```

It can take a while because gitlab has many embaded sercies like gitlay server, nginx etc.

Now time for login into gitlab WebUi. Using firefox or chrome and type url:

```
http://localhost
```

![](./images/gitlab-login.png"")
