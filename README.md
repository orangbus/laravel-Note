# laravel study note

```
composer require laravel/ui --dev
php artisan ui [vue] --auth
npm install
```

## 学习目标

- laravel结合vue页面渲染
- 登录验证
- 邮件发送
- Markdown页面渲染
- 文件上传

成果：在线视频解析-导航网站

## Package

```
layuimini:https://github.com/zhongshaofa/layuimini
```



Github：https://github.com/orangbus/laravel-App.git

更新脚本：

```
#!/bin/bash
# 请将此代码全部复制到项目根目录下的 [ go.sh ]文件中执行
echo "===== orangbus.cn 一键提交github ===="
#Config
# 自己想要提交的 github 地址
github="https://github.com/orangbus/laravel-App.git"

function updata()
{
    git add .
    read -p "请输入Commit信息：" VAR
    echo "你输入的message:" $VAR
    git commit -m $VAR
    git remote add origin $github
    git push -u origin master
    echo "Update is complate!"
    # 记录每次提交日志
    logFile="./Log.txt"
    if [ -e $logFile ]
    then
        echo "+ 日志文件已存在。"
    else
        touch Log.txt
        if [ "$?"="0" ]
        then
            echo "+ 【Log.txt】文件创建成功！"
        else
            echo "- 文件创建失败，请手动在当前目录创建一个【Log.txt】文件"
        fi
    fi

    echo "`date`:$VAR" >> Log.txt
    if [ "$?"="0" ]
    then
        echo "日志写入成功！"
    else
        echo "日志写入失败！"
    fi
}

updata

```

