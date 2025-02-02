# 使用 Node.js 作为基础镜像
FROM docker.1ms.run/library/node:18-alpine

# 设置工作目录
WORKDIR /app

# 安装 hexo-cli
RUN npm install -g hexo-cli

# 复制 package.json 和 package-lock.json (如果存在)
COPY package*.json ./

# 安装依赖
RUN npm install

# 复制整个项目
COPY . .

# 清理并生成静态文件
RUN hexo clean && hexo generate

# 启动 Hexo 服务器
CMD ["hexo", "server"]