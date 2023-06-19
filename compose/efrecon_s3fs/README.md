efrecon/s3fs

https://hub.docker.com/r/efrecon/s3fs
https://gist.github.com/HeshamMeneisi/a3f96183cac25cf5979465b3cddef315

```
# Tip: You can just define all environment variables used here in a 
# .env file in the same directory so as not to expose secrets
# docker-compose will load it automatically
services:
  s3fs:
    privileged: true
    image: efrecon/s3fs:1.86
    restart: always
    environment:
      - AWS_S3_BUCKET=${AWS_S3_BUCKET}
      - AWS_S3_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID}
      - AWS_S3_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY}
      # A workaround for bucket names containing '.' until the related s3fs-fuse issue is resolved
      # Keep in mind this is a secrutiy risk (default is https)
      # - AWS_S3_URL=http://s3.amazonaws.com
    volumes:
    # This also mounts the S3 bucket to `/mnt/s3data` on the host machine
      - ./public/uploads:/opt/s3fs/bucket:shared

  test:
    build: .
    restart: always
    depends_on:
      - s3fs
    # Just so this container won't die and you can test the bucket from within
    command: sleep infinity
    volumes:
      - /mnt/s3data:/data:shared

```

测试
```
docker run -v ~/docker-app/s3fs/uploads:/srv -p 9080:80 filebrowser/filebrowser

docker run --rm --name=files -v ~/docker-app/s3fs/uploads:/srv -p 9080:80 filebrowser/filebrowser
```