[English]
Dash delimited format
a comma-separated list of parameters
touch base - to talk to someone for a short time to find out how they are or what they think about something
GUID - Globally Unique Identifier
UUIU - Universaly Unique Identifiers
backwards compatibility with previous version of Rex API
The US government no longer recognizes SHALL as a legal term and recommends using MUST instead.
When used in a question, which form more often indicates that the asker is hesitant? - should
a bona fide sample of Lincoln's handwriting - authentic, true
Leave everything exactly as it is.
We have enough to do as it is without your latest orders!
Be open to learning new things
Before we make any decisions today, I'd like to make sure that everyone is on the same page.
This could be done better
Don't you dare!

a forward slash (/) character
a backslash (\) character

Telfast - hayfever
Belair + Glenelta + Blackwood

do the shoey - 
flat out - super busy and tired
btw - by the way
lol - laugh out loud
lmk - let me know
imo - in my opinion
roger - your message has been received
fyi - for your information
brb - (I'll) be right back
afaik - as far as I know
tbc - to be confirmed
tba - to be announced
tbh - to be honest

[Books needed]
A Practical Guide to Linux Commands, Editors, and Shell Programming; Edition. 4th - Michael

[bug] 
When only E2V campaign is booked, nothing is shown on the Display but the AP logo, and "connected" button is orange
When E2V + normal campaign are booked, both campaign and e2v are shown on the Display, and "connected" button is green

[bug]
Sid - Forty Winks - Narre Warren (Pro)
		- CarSwap-VIC
		- Genesis Fitness - Caulfield (Pro)
		Downloading (2) files:
		Genesis_FitnessHealth_ProLED_30daysTransform.jpg 0%
		Genesis_FitnessHealth_ProLED_ReformerPilates.jpg 0%
		45422918-E8CB-4BE0-B213-C350E9AAED31.png

[Linux - tty]
Ctrl + Alt + F1~F6 switch between different users;
Debian GNU/Linux 10 ac-master tty2

在大多数 发行版 中，你可以使用以下键盘快捷键来得到 TTY 屏幕：

CTRL + ALT + F1 – 锁屏 / Zotac-TTY1
CTRL + ALT + F2 – 桌面环境 / Zotac-LCD
CTRL + ALT + F3 – TTY3
CTRL + ALT + F4 – TTY4
CTRL + ALT + F5 – TTY5
CTRL + ALT + F6 – TTY6
你最多可以访问六个 TTY。但是，前两个快捷方式指向发行版的锁定屏幕和桌面环境。

[E2V dev]
// newsapiorg.php

// new E2V for Cyrus
	- database: carswap root/OES12345@
	- tables: cs_car + cs_users + cs_images + dealer_slots + dealer_screens
	- dealer's picture: https://api.carswap.me/e2v/logos/122809.png - not in use

1. agent name from database or UI
2. https://api.carswap.me/e2v/cs_lorbek_v.php
3. 图片位置调整
4. 去掉白色背景图
5. 字体更新
6. 加上agent名字
7. 换 Carswap logo

[Ray White E2V]
	- A new boss means new api-key and token 9/12

[todo]
// debug global event bus
// https://blog.huati365.com/9dc7d6666f2709ad - AnyEvent

[Linux - service]
...

[connect E2V to a Display]
	post - http://localhost:8000/api/v1/scheduleSource
	get  - http://localhost:8000/api/v1/displays?include=bookings,e2vbookings,tags&limit=all&team=353
	get  - http://localhost:8000/api/v1/campaigns?include=tags,media&limit=all&team=353
	get  - http://localhost:8000/api/v1/sources?limit=all&team=353
[delete E2V from a Display]
	delete - http://10.1.1.238:8000/api/v1/displays/6675/sources/692
	get - displays 同上
	get - campaigns
	get - sources
	
[make a campaign]

[uploading a png]

	1. click 'upload' on localhost:8080 
		- axios.post(UPLOAD_ENDPOINT)
		- 1. nerkmid receives the file and Beginning conversion of image from $.../conv/in/filename to $.../conv/out/filename.png
		- 2. Creating thumbnail filename_l.jpg, filename_m.jpg, and filename_s.jpg in  $.../conv/thumb/
		- 3. Sending callback to API
		- 4. Sending API request to store media
	2. axios.get(UPLOAD_POLL_ENDPOINT)
		- ```
		  response: {
			stauts:200, 
			statusText:"OK", 
			config:{url:"http://localhost:8008/status"},
			data: {hash: "b735153d8bbc495b22ea4d5d52c9ae83"}
			}
		  ```
	3. click an image: request URL - http://10.1.1.238/out/7e8265381303728d832e1d75a791d184.png

[Media / refresh]
http://localhost:8000/api/v1/media?limit=all&search=&team=353
```
	...
	{
	   "mediaId":"1063843",
	   "teamId":"353",
	   "imageId":"15639",
	   "name":"5188a01e8f98e4e553ded995908d5cea.png",
	   "size":"68498",
	   "height":"755",
	   "width":"1025",
	   "hash":"b735153d8bbc495b22ea4d5d52c9ae83",
	   "mimeType":"image\/png",
	   "uri":"http:\/\/localhost\/out\/5188a01e8f98e4e553ded995908d5cea.png"
	}
	...
```
http://localhost/thumb/b735153d8bbc495b22ea4d5d52c9ae83_l.jpg


1.png 200
	https://aws.adverpost.com/ccda4afcbad22a95e3bc27d7e6bee980.png 
PFS_VideoScreen_384x240px_6c_.jpg
	https://aws.adverpost.com/2779d5953353fa92e04f89af8b65dbf4.png
0b79f1bc81a936eecc3810aa0b493f6e.png
	http://localhost/out/0b79f1bc81a936eecc3810aa0b493f6e.png
ed7bb012952ab8aba1fec4ee038d6ead.png	
	http://localhost/out/ed7bb012952ab8aba1fec4ee038d6ead.png
	
[ufw]
```bash
$ sudo ufw status verbose 
$ systemctl status ufw
$ ufw enable
$ sudo ufw allow http
$ sudo ufw allow 80
$ sudo ufw allow 8000
```
	- UFW防火墙的默认行为是阻止所有传入和转发流量，并允许所有出站流量。这意味着除非您打开指定的端口，否则任何尝试访问您的服务器的人都将无法连接。
	- 默认策略在/etc/default/ufw文件中定义，可以通过手动修改该文件或使用sudo ufw default <policy> <chain>命令来更改。
	- 根据系统上运行的应用程序，您可能还需要打开其他端口。 打开端口的一般语法是ufw allow port_number/protocol。如果未给出协议，则UFW会同时为tcp和udp创建规则。


[IRC] 
	Internet Relay Chat
	IRC Client
	IRC Server
	
[HexChat / IRC]
1. all commands are in 00.html / External API
2. Server: root.cdn.adverpost.com

http://root.cdn.adverpost.com:2222/clients

[connect to zotac]
```bash
$ ssh root@10.1.1.134
// password + enter
root@ac-master:~# systemctl start apn
root@ac-master:~# logout

root@ac-master:~# top
root@ac-master:~# cd /
root@ac-master:~# cd hadaly
root@ac-master:~# ls
// adclient  AnyEvent  assets  bin  cache	Data  DISCLAIMER  docs	Hadaly	IO  opt
root@ac-master:~# cd Hadaly
root@ac-master:~# ls
// Blocking.pm  Config.pm	Listener.pm  Playlist.pm  System.pm  Util.pm
root@ac-master:~# nano Config.pm
root@ac-master:~# systemctl restart ac
root@ac-master:~# systemctl status ac
```
A guide to Login as root over SSH on Ubuntu
https://www.linuxfordevices.com/tutorials/ubuntu/login-as-root-over-ssh
```bash
//  To check if we have an ssh-server is installed on our target machine
root@ac-master:~# apt-cache policy openssh-server
// Install ssh-server
root@ac-master:~# sudo apt install openssh-server
root@ac-master:~# systemctl status ssh
root@ac-master:~# sudo systemctl enable --now ssh
// edit /etc/ssh/sshd_config --> PermitRootLogin yes + PubkeyAuthentication yes
root@ac-master:~# sudo systemctl restart ssh
```

[mailgun]
```bash
curl -s --user 'api:YOUR_API_KEY' \
    https://api.mailgun.net/v3/YOUR_DOMAIN_NAME/messages \
    -F from='Excited User <mailgun@YOUR_DOMAIN_NAME>' \
    -F to=YOU@YOUR_DOMAIN_NAME \
    -F to=bar@example.com \
    -F subject='Hello' \
    -F text='Testing some Mailgun awesomeness!'
```

```php
$mgClient = Mailgun::create($this->di->getConfig()->mailgun->apiKey, $this->di->getConfig()->mailgun->apiUrl);
$params = array(
	'from'    => $this->di->getConfig()->mailgun->from,
	'to'      => $this->di->getConfig()->mailgun->adminAccount,
	'subject' => 'Pending Manual Approval',
	'html'    => $this->view->getRender('emails', 'ManualApprovalEmail', [
		"email" => $email,
		"username" => $username,
		"userId" => $user->getId()
		])
);
try {
	$mgClient->messages()->send($this->di->getConfig()->mailgun->domain, $params);	
} catch (\Exception $e) {
				return $this->respondServerError('The server failed to process your request');
			}
```

[New Zotac]
How to make a new copy of Zotac
	- a new empty Zotac + a new M2 Hard disk 

	[no use most of the time]
		- U plugged into Zotac and starts system
		- find AdverClient in two ways
			1. download from https://docs.adverpost.com 
			2. desktop when the system is ready 
	- Hard Disk connected to the computer next to Michael
	- double-click Adverclient(adclient-318-amd64.img.xz) --> target new Hard disk
	
	- a warning window appears + fix
	- system / GParted -- choose the 2nd part(apclient) + expand the volume to 120G	
	
	- put the Hard Disk in the Zotac
	- connect the Zotac to a screen --power_on--> show HWID 113.189.1b2
	- delete --> BIOS setting: Power/Loss - on, 
				   Security/Secure boot/Secure boot - disabled, secure mode - custom,
	                           Boot - legacy --> win8 or Pure UEFI

	- check HexChat / noconf / :*:getID + :*:clearState
	- Add a new Display on adverpost + change ACID to TEST.****
		- LED: pixel is useful, physical width and height only for users 
		- LCD: 0×0 -- use the maximum by default 
		- block time -- the maximum of a campaign supported
		- Brightness / censor -- not finished yet
		- ACID connected to IRC, not for users, can be renamed to something meaningful
	- check HexChat / noconf: h_14... has quit --> / #au: TEST

	- Ctrl + Alt + F1: enter cmd window
	- root / elitem
	- hadaly/Hadaly/System.pm  --> http://10.1.1.238:8000
	- nano "..." interface=%s --> "eth1" // Ln:66 or "eth0"
	- systemctl restart ac
note:
	- On a LCD, contents can be rotated: 
		Displays / A-TEST / Edit / Type:LCD + Pixel Width/Height:0 + Screen Rotation: 180
	- change wifi password to custom
		nano /etc/wpa_supplicant.conf
		network={
		ssid="name"
		psk="pwd"
		}		
		

[DHCP and DNS]
DHCP 
	- Dynamic Host Configuration Protocol
	- Assigns IP addresses to hosts
	- Comes as a client and a server
	- DHCP Discover + DHCPOffer + DHCPRequest + DHCPACK
	- DHCPDiscover - Looks for a DHCP server
	- DHCPOffer - The DHCP server offers an address
	- DHCPRequest - The host requests to lease the address
	- DHCPACK / sends < IP addr + subnet mask + the default gateway + dns server >
	- UDP Port / Client 68 + Server 67
OpenWrt luci feed 
	- LuCI - OpenWrt Configuration Interface
	- https://github.com/Lisa-NJ/luci
UPD (User Datagram Protocol)
	- UDP ports include the DNS port (53), the Dynamic Host Configuration Protocol port (68), and the Kerberos port (88)
dnsmasq

MAC Address
	- media access control address
	- a unique ID assigned to network interface cards (NICs)
	- also known as a physical or hardware address

[LAN]
LAN cable - Local Area Network
Ethernet cables can have different lengths, colors and transmission speeds. But they all have one thing in common: they have an RJ45 connector at both ends.

[linux shortcut]
```
Ctrl+Alt+T ==> open the terminal
Window + <-/-> ==> left half / right half
Ctrl+R ==> reverse-i-search

```
[Postman]
Cloud Agent Error: Can not send requests to localhost. Select a different agent.
	- 不能给 localhost 发请求

[Rex API]
	- The Rex application is accessible at https://app.rexsoftware.com
	- The API supports 2 headers - Authorization and X-api-option
	- The token is GUID which represents the session you are logged into. 
	- The X-api-option header allows you to specify options that modify the API request and response handling.

```js
fetch("https://api.rexsoftware.com/v1/rex/Contacts/read", {
  body: JSON.stringify({id: 1}),
  headers: {
    "Accept": "application/json, text/javascript, */*; q=0.01",
    "Authorization": `Bearer ${YOUR_TOKEN}`,
    "Content-Type": "application/json",
    "X-Api-Option": "use_status_codes=true,add_request_prefixes=true,use_strict_arguments=false,strip_response_prefixes=false"
  },
  method: "POST"
}).then(response => response.json())
```

```bash
curl --request POST \
  --url https://api.rexsoftware.com/v1/rex/Contacts/read \
  --header 'accept: application/json, text/javascript, */*; q=0.01' \
  --header 'authorization: Bearer ${YOUR_TOKEN}' \
  --header 'content-type: application/json' \
  --header 'x-api-option: use_status_codes=true,add_request_prefixes=true,use_strict_arguments=true,strip_response_prefixes=true' \
  --data '{"id": 1}'
```

[REST API & RPC API]
- https://www.geeksforgeeks.org/difference-between-rest-api-and-rpc-api/

REST APIs
	- Representational State Transfer
	- A REST API endpoint is a URL that utilizes HTTP verbs to execute CRUD (Create Read Update Delete) operations over the resources. These HTTP verbs are GET, POST, PATCH, PUT and DELETE. It focuses on providing resources from the server to the clients. 
	- Allows Standard-based protection with the use of OAuth protocols to verify REST requests.
	- payload is quite big hence the entire files get back while you needed one field
	- loses the ability to maintain state in REST

RPC APIs
	- Remote Procedure Call 
	- They have lightweight payloads, therefore, provides high performance
	- easy to understand and work as the action is part of the URL
	- it is not well standardized

```
                  REST                                                  RPC
   1    REST is resource-oriented.	                       RPC is action-oriented.
   2    Supports GET, POST, PUT, PATCH, and DELETE.            only supports GET and POST
   3    It provides flexibility for hardware architecture      no flexibility in RPC for hardware architecture
   4    It supports hypermedia and hyperlinks                  It does not supports hypermedia and hyperlinks
   5    Allows to specify Content-types or accept headers      Require payloads of a few data types as XML for XML-RPC.

```


[Payload within an API]
 - https://blog.hubspot.com/website/what-is-payload
Payload is the data you send over the computer network. 
```
data ----- overhead - to show the source or destination of the payload, is removed from the view once reaching its destination
       |
       --- payload - the body of your HTTP request and response message when you make an API request.
```

[call API - browser]
http://localhost/weather.php?_path=/status
http://localhost/weather.php?_path=/parameters
http://localhost/weather.php?_path=/getShedule
https://newsapi.org/v2/top-headlines?apiKey=bcdc50d80ac04d7a9afcaee612146a7b&q=apple <!-- news -->

[call API - cmd / curl]
``` bash
$ curl http://localhost/weather.php?_path=/status
$ curl http://localhost/weather.php?_path=/parameters
$ curl http://localhost/weather.php?_path=/getSchedule -X POST -d '{"api_key":"ce79aef7a491450082040610222607", "location":"Australia/Adelailde", "duration":10}' | tail -n1 > output
$ jq . output
$ curl http://localhost/test-lisa.php?_path=/status
$ curl http://localhost/test-lisa.php?_path=/parameters
$ curl http://localhost/test-lisa.php?_path=/getSchedule -X POST -d '{"duration":5}' | jq . 
```
[call API - code / php]
``` php
	$baseurl = 'https://newsapi.org/v2/top-headlines';
	$api_key = 'bcdc50d80ac04d7a9afcaee612146a7b';
	$queryStr = 'apple';

	$api_key = urlencode($api_key);
	$userAgent = $_SERVER['HTTP_USER_AGENT'];

	$req = curl_init($baseurl . "?apikey=$api_key&q=$queryStr");  // 'api_key'&'q' - from api provider
	curl_setopt($req, CURLOPT_RETURNTRANSFER, TRUE);
	curl_setopt($req, CURLOPT_USERAGENT, $userAgent);
	$output = curl_exec($req);

	file_put_contents($cache_name, $output);

	$json = json_decode($output, true);

	$newsArr = $json['articles'];
```


[API]
https://www.youtube.com/watch?v=Yzx7ihtCGBs&t=6
	- The system we want to communicate with
	- We can't access the internals of the system
	- We can only talk to the API layer
	- End point / input required + result
	- API Key: a unique ID to identify your App

[APT]
APT (Advanced Package Tool) is the command-line tool to interact with this packaging system. There are already dpkg commands to manage it, but apt is a more user-friendly way to handle packages. You can use it to find and install new packages, upgrade packages, clean your packages, etc.

There are two main tools around APT: apt-get and apt-cache. apt-get is for installing, upgrading, and cleaning packages, while apt-cache command is used for finding new packages. 

[memcached]
A distributed memory cache system that speeds up dynamic Web applications thanks to Memcached, an open source, distributed application cache system. In order to avoid accessing external databases and APIs regularly, the system caches the data and objects in memory.

[Chrome]
F12 --> Inspect on Chrome
Inspect / network / headers --> see the server infor

Apache, IIS, Nginx, sffe
If the website uses CDN -- Cloudflare
website uses HTTP accelerator -- Varnish

[curl]
GitHub - forked curl.md
$ curl -X POST -H -d ...

Charlie's
```
\1. Environment setting up for run and dev && How to check for each one? Phalcon + mariadb

你可以直接run api那个后端看是否能启动，如果有报错查看具体报错

或者 通过$ php -m  查看现有modules，你之前看到的那个文件里应该有list所有需要的modules.

Mariadb直接安装就可以了，但是api里面有个配置文件具体名字我忘了，里面需要修改连接的账号密码和端口，如果有问题的话你在run api 服务器的时候也会报错. 但是本地的DB copy我没有，当时我没有服务器的访问权限,他们直接给了我一个DB的copy.

具体的安装我记得当时是参考的这个网站一步步安装的

https://docs.phalcon.io/4.0/en/installation


\2. Structure of E2V-related modules, helper-public && helpers

主要就是helpers那个文件夹里有几个function调用，其余的没用.

那几个functions的作用也只是格式化数据类型为zotac那一端能读懂的类型播放。helper-public那个文件夹差不多就算是helper的README, 单纯告诉你要怎么样的格式. 实际上你如果按照那个格式手写个txt给zotac也能放。


\3. What skills to learn at this stage and route?

主要先把环境搭好能把api和vue两个run起来,后面主要看看vue就行。我在那上班的时候基本上没动过api那一端，他们也基本没怎么动，都是原来写好的,也没人愿意大改。


\4. Add another public API means:？

比如现在有天气的，real estate的，carswapde，应该是指老爷子想再找个public api的接口拿数据再做一个e2v的内容吧，


\5. how to debug？

后端那一块基本就看run api server的terminal报错，以及前端浏览器里response的内容了

前端就直接看浏览器的报错了.


a current example
Concepts - pipe the output to jq - ? / E2V-compatible endpoint = public API ?

E2V Debug直接run那个php文件就能显示报错，或者你从浏览器通过url打开那个文件并且调用参数，如果需要。


\6. Other parts? - DealCodes / AWS / IRC

这几个先不用管了，老爷子天天说这个，但是具体是什么东西都没人知道。

Dealcodes目前有一个项目，但是那个只是测试的，没有太多东西，很久没人维护了，modules很多都过期了，还不如重写

```

[Apache2]
```
/etc/apache2/
|-- apache2.conf
|       `--  ports.conf
|-- mods-enabled
|       |-- *.load
|       `-- *.conf
|-- conf-enabled
|       `-- *.conf
|-- sites-enabled
|       `-- *.conf
```
[Apache2 vs Nginx]
https://kinsta.com/blog/nginx-vs-apache/#nginx-modules
The biggest difference -- the way they handle requests
	1. Apache processes requests with MPM-s 
	2. ginx uses asynchronous, non-blocking event-driven architecture
Apache uses processes for every connection.

[Composer]
https://linuxize.com/post/how-to-install-and-use-composer-on-debian-10/
Composer is a dependency manager for PHP (similar to npm for Node.js or pip for Python ).
```
$ sudo apt update
$ sudo apt install wget php-cli php-zip unzip <!-- have the necessary packages installed -->
$ wget -O composer-setup.php https://getcomposer.org/installer <!-- Download the installer -->
$ sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```

[MySQL / MariaDB]
MySQL is one of the popular and most common database servers using to store data. 
MariaDB is the fork of MySQL. 
	==> the commands used for Oracle MySQL will also be applicable for MariaDB.
```
$ mysqld --version  <!-- to check version -->
$ mysqladmin -V 
$ sudo mysql
```
How to install?
<!-- 1. Adding mariaDB repository -->
$ sudo apt-get update
$ sudo apt-get install lsb-release software-properties-common <!-- necessary software -->
$ sudo apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'  <!-- import the repo key to system -->
$ sudo add-apt-repository "deb [arch=amd64] http://mirror.23media.de/mariadb/repo/10.4/debian $(lsb_release -cs) main"  <!-- add the mariaDB repo to source list -->
<!-- 2. Installing mariaDB -->
$ sudo apt-get update
$ sudo apt-get install mariadb-server
<!-- 3. Checking mariaDB stauts -->
$ sudo systemctl is-enabled mariadb
$ sudo systemctl is-active mariadb
$ sudo systemctl status mariadb <!-- active 10.5.15 -->
<!-- 4. Testing mariaDB connectivity -->
$ sudo mariadb -u root -p
MariaDB $ SELECT VERSION();
MariaDB $ SHOW DATABASES;
MariaDB $ exit;

[Nginx]
Nginx does not have a configuration system like Apache;
Nginx is very efficient in serving static content on its own.
Nginx uses asynchronous, non-blocking event-driven architecture.
Nginx ideally has one worker process per CPU/core. Each one can handle hundreds of thousands of incoming network connections per worker. There is no need to create new threads or processes for each connection.
```
$ pcre-config --version
	8.44
$ cd /usr/sbin
$ nginx
$ nginx -v       <!-- nginx/1.18.0 -->
$ ps -aux|grep nginx
$ nginx -s quit
$ nginx -s reload
$ sudo nginx -t  <!--to check config file-->
```
PCRE: for Nginx to Rewrite
/usr/share/nginx/html/index.html

edit etc/nginx/sites-avaliable/default
```
server {
	listen 80;
	server_name localhost;
	autoindex on;
	index index.php;
	root /home/tanami/helpers; # CHANGE THIS
	location ~ \.php$ {
		include /etc/nginx/fastcgi.conf;
		fastcgi_split_path_info  ^(.+\.php)(/.+)$;
		fastcgi_param PATH_INFO  fastcgi_path_info;
		fastcgi_param PATH_TRANSLATED $document_root$fastcgi_path_info;
		fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
		try_files $uri =404;
		fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
		fastcgi_read_timeout 600;
		fastcgi_intercept_errors on;
		gzip off;
		fastcgi_index  index.php;
	}
}

```
	在Nginx的官方文档中定义的location的语法结构为：
	
	location [ = | ~ | ~* | ^~ ] uri { ... }
	其中，uri变量是待匹配的请求字符串，可以是不含正则表达的字符串，如/myserver.php等；也可以是包含有正则表达的字符串，如 .php$（表示以.php结尾的URL）等。为了下文叙述方便，我们约定，不含正则表达的uri称为“标准uri”，使用正则表达式的uri称为“正则uri”。
	
	其中方括号里的部分，是可选项，用来改变请求字符串与 uri 的匹配方式。在介绍四种标识的含义之前，我们需要先了解不添加此选项时，Nginx服务器是如何在server块中搜索并使用location块的uri和请求字符串匹配的。
	
	在不添加此选项时，Nginx服务器首先在server块的多个location块中搜索是否有标准uri和请求字符串匹配，如果有多个可以匹配，就记录匹配度最高的一个。然后，服务器再用location块中的正则uri和请求字符串匹配，当第一个正则uri匹配成功，结束搜索，并使用这个location块处理此请求；如果正则匹配全部失败，就使用刚才记录的匹配度最高的location块处理此请求。
	
	了解了上面的内容，就可以解释可选项中各个标识的含义了：
	
	“=”，用于标准uri前，要求请求字符串与uri严格匹配。如果已经匹配成功，就停止继续向下搜索并立即处理此请求。
	
	“^～”，用于标准uri前，要求Nginx服务器找到标识uri和请求字符串匹配度最高的location后，立即使用此location处理请求，而不再使用location块中的正则uri和请求字符串做匹配。
	
	“～”，用于表示uri包含正则表达式，并且区分大小写。
	
	“～*”，用于表示uri包含正则表达式，并且不区分大小写。注意如果uri包含正则表达式，就必须要使用“～”或者“～*”标识。

[install google chrome]
Ctrl+Alt+T ==> open the terminal
Ctrl+Shift+Delete ==> clear the cache

```
$wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
$sudo apt install ./google-chrome-stable_current_amd64.deb
```

[install multiple node versions with nvm]
```
$wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
// close and reopen Terminal
$nvm -version
 => v0.38.0
$nvm install node //install latest NodeJs version
$nvm use node 
 => now using node v18.6.0 (npm v8.13.2)
$nvm ls //get a list of installed NodeJs version
$nvm exec 8.11.1 node app.js //use specific version without switching
$nvm use system //use installed nodeJs version in the system
```

[VS code]
F12 - Inspect
Alt + up - move current line up
Ctrl + D - select the same words one by one
Ctrl + Shift + ` - Terminal
Ctrl + Shift + P - fast path
Ctrl + Home / End - Beginning and End of a file
Ctrl + Shift + I - json

On Windows: Shift + Alt + F
On Mac: Shift + Option + F


[curl]
curl command is a tool to download or transfer files/data from or to a server using FTP, HTTP, HTTPS, SCP, SFTP, SMB and other supported protocols on Linux or Unix-like system.
```
$ curl --version
$ curl -I https://www.google.co.in/
$ man curl
$ curl --help
```

[flight]

		Singapore --> Shanghai    Monday   ￥2000
Adelaide <---   Singapore                 Sunday   ￥1600
