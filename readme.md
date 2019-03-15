command lines

`docker --version`

`FROM <base_image>:<phiên_bản>` : đây là câu lệnh bắt buộc phải có trong bất kỳ Dockerfile nào. Nó dùng để khai báo base Image mà chúng ta sẽ build mới Image của chúng ta.

`WORKDIR /app`: thư mục làm việc.

`COPY . /app` : sao chép nội dung của thư mục hiện tại vào container tại thư mục `/app`.

`RUN <câu lệnh>`: sử dụng lệnh này để chạy một command cho việc cài đặt các tool, libraries cần thiết cho ứng dụng.

`CMD <câu lệnh>`: trong một Dockerfile thì chúng ta chỉ có duy nhất một câu lệnh CMD, câu lệnh này dùng để xác định quyền thực thi của các câu lệnh khi chúng ta tạo mới Image. lệnh `CMD` sẽ thực thi sau khi các lệnh `ENTRYPOINT` 

`ENTRYPOINT <câu_lệnh>:` định nghĩa những command mặc định, cái mà sẽ được chạy khi container running.

`ENV <tên_biến:biến>`: định nghĩa biến môi trường trong Container.

`docker system prune`: Xóa hết tất cả các containers.

`docker images -a` : list tất các các images

`docker ps -a` : list tất cả các containers.

`docker rm ID_or_Name ID_or_Name`: xóa một container theo id hoặc tên.

`docker container stop container_ID`: stop một container.

`docker container kill container_ID`: kill một container.

[Tham khảo tại ](https://docs.docker.com/get-started/part2/)

#### fix lỗi không kill/stop được container
https://stackoverflow.com/questions/47223280/docker-containers-can-not-be-stopped-or-removed-permission-denied-error

#### fix lỗi DNS không cài đặt được tool, libraries 

https://docs.docker.com/get-started/part2/


#### Docker Compose
[Tham khảo docker compose](https://docs.docker.com/get-started/part3/)



`docker service ls`: List service

`docker service ps getstartedlab_web`: List the tasks for your service:

```
docker stack ls                                            # List stacks or apps
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file
docker service ls                 # List running services associated with an app
docker service ps <service>                  # List tasks associated with an app
docker inspect <task or container>                   # Inspect task or container
docker container ls -q                                      # List container IDs
docker stack rm <appname>                             # Tear down an application
docker swarm leave --force      # Take down a single node swarm from the manager
```