<h1>Git和Github的使用</h1>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>21-3-6
<hr>
<p>说来惭愧，作为计算机专业的学生，一直没怎么用过Github来写项目，大多数时候是用Download下载别人项目，之前做课设也是重命名很多份文件夹，把自己头都弄晕了，不管是为了找工作，还是维护计算机学生的尊严，都很有必要学一下Git常用命令，然后使用Git和Github撸一个项目，老话说得好，种一棵树最好的时间是十年前，然后是现在。开始吧。</p>
<p>首先注册Github账号并且在电脑下载Git，这个工作是我在很久之前就已经完成的，自己也忘了当时怎么弄得了。然后在Github网站上创建一个Respository,复制Url,在自己电脑上新建一个文件夹，git clone + url一下，之后新建一个test.js文件尝试一下，随便写点东西，git add test.js,然后git commit -m '第一次提交test.js'，尝试git push一下，可能会报错，那是因为当时我在网站上按照引导创建了一个readme.md,但是本地没有更新，导致本地的项目不是最新的，无法Push,因此需要先git pull把本地和Github上面的文件下同步一下，然后就可以顺利git push了，在github网站上刷新可以发现项目中有了test.js文件，同时本地也有了readme.md文件。</p>
总体来说，git代码如下:<br>
<code>
git clone + url<br>
git add test.js<br>
git commit -m '第一次提交test.js'<br>
git pull<br>
git push<br>
</code>
<p>
其实按照上面的步骤多少还是有点问题，比如git pull或者git push的时候，可能会报错，目前推测是墙的问题（不然不会有时可以有时不可以)，也可能是ssh的问题，但是ssh我是很久之前配置的了，现在已经忘了怎么弄得当时，这个问题暂时留着。
</p>
<p>
奇怪的错误再次发生，使用git clone + url时，报以下错:
<pre>
OpenSSL SSL_read: Connection was reset, errno 10054
</pre>
以及
<pre>
 Failed to connect to github.com port 443: Timed out
</pre>
呵呵哒，百分百跟防火墙有关系，虽然报错但是最终还是clone上去了，头疼。目前来看用管理员权限打开命令行是可以用的。
</p>
<p>
今天又遇到一个问题，明明是自己建的仓库自己commit的，但是在github上面显示commit的账户是我之前的账号，有点头疼
</p>
<p>
<img src="./images/git_problem.png" width="300px" height="200px">
</p>
<p>
使用以下代码查看自己git绑定的账户，可以看到:
<pre>
git config user.name
git config user.email
</pre>
绑定的其实还是之前的账户，更新之后:
<pre>
git config --global user.name "zhangsan(新的用户名)"
git config --global user.email "123456@qq.com(新的邮箱)"
git config --global user.password "123456(新的密码)"
# 这里的zhangsan和邮箱都是你修改之后的用户名和邮箱
</pre>
</p>
<p>
再次尝试，发现没有问题了。
</p>
<hr>
<p>今天发现git是无法上传空目录的，因此如果想上传空目录，必须要在空目录中新建一个无关文件</p>
<hr>
<p>github中要删除仓库，可以打开该仓库，然后点右边的settings(注意是insights旁边的settings),然后一直划到最下面点击delete并且输入验证码就可以了。</p>
<hr>
<p>github要查看提交记录也非常简单，直接点旁边的数字+commits选项就可以看到了</p>