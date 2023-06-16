Github
https://github.com/gptlink/gptlink
https://github.com/gptlink/gptlink-deploy

docker run -it --rm -p 8040:80 \
   --name=gptlink \
   -e DB_HOST="192.168.2.99" \
   -e DB_DATABASE="gptlink" \
   -e DB_USERNAME="root" \
   -e DB_PASSWORD="root@123" \
   -e REDIS_HOST="192.168.2.99" \
   -e REDIS_PORT="6379" \
   -e OPENAI_PROXY_HOST="192.168.2.21" \
   -e OPENAI_PROXY_PORT="7890" \
   -e JWT_SECRET="wY3f28d8Wq4md2dNuXPHEdUccv2YWbKf"
   overnick/gptlink

测试
 

ENV 环境
https://github.com/gptlink/gptlink/blob/master/docs/ENV.md

在线随机字符串/安全密码生成工具
http://tools.jb51.net/aideddesign/rnd_mima_tool


composer
https://www.composerize.com/