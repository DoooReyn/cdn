## CDN更新 ##
1，client同步到最新，去png图片警告(libpng.bat)，资源压缩、打包大图(TexturePacker)。

2，version目录中，脚本加密/一键批处理(src+res)，git确认筛选需要更新的资源，生成MD5码，最后发布到中间仓库(cdn)并提交(client与server互通仓库)。

3，x-shell连接到cdn服务器，cd到对应目录，git pull拉取client刚提交的资源。

4，登入云服管理页面(腾讯云)，刷新需要更新的资源文件(logx.ini里 + project.manifest文件，version.mainfest文件不需要刷新，因为目前它只放在源站，没放云服CDN)。

## android出包 ##
1，从中间仓库cdn取最新res，src，project.manifest资源替换assert目录下对应文件，手动修改version.mainfest中版本号(与云服不同)。

2，eclipse打包(export，签名，输出)。

