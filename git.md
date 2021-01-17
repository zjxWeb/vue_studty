# github的使用

1. 配置ssh

	+ `git config --global --list `验证邮箱与用户名
	+ 通过git config --global user.name “yourname”，git config --global user.email “email@email.com ”（这里得名字和邮箱都是注册github时用的）设置全局用户名和邮箱。
	+ ssh-keygen -t rsa -C + “你自己的邮箱”
	+ .ssh/id_rsa.pub 用记事本打开，并黏贴到 github-settings-ssh and GPS keys 

