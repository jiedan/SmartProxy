# SmartProxy
安卓下的智能代理


最简配置：  
  
\#必须至少包含一行proxy信息，默认仅访问国外网站才会代理，国内直连。  
\#目前支持HTTP(CONNECT)和Shadowsocks(table加密)两种代理。  
\#可以设置多个代理，但是目前系统只会使用第一个。  

\#需要用户名密码验证的代理服务器地址  
proxy http://username:password@hostname:port  
 
\#无需验证的代理服务器  
proxy http://hostname:port   

\#shadowsocks地址（目前method仅支持table）  
proxy ss://method:password@hostname:port  

\#Base64加密的shadowsocks地址（目前method仅支持table）  
proxy ss://YmYtY2ZiOnRlc3RAMTkyLjE2OC4xMDAuMTo4ODg4  
          
完整示例：  

\#smartproxy config file  
\#字符'#'用于注释  
\#参数每行一条，参数名称和值之间用空格分隔，使用"name value1 value2 ... valueN"格式。  
\#同一参数名称可以在多行出现，系统会将其值自动合并成一个数组。  

\#TAG:session_name   
\#设置VPN连接会话名称。默认值：无。非必须。  
session_name smartproxy  

\#TAG:welcome_info  
\#设置VPN连接后的欢迎信息。默认值：无。非必须。  
welcome_info Welcome to smartproxy!  

\#TAG:ip  
\#设置VPN的IP地址。默认值：10.8.0.2。非必须。  
ip 10.8.0.2  

\#TAG:dns  
\#设置VPN的DNS地址，设置后系统将使用该DNS，若不设置系统将使用原来的DNS。默认值：无。非必须。  
dns 114.114.114.114  
dns 8.8.8.8  

\#TAG:dns  
\#DNS缓存时间，单位秒，用于防DNS污染。默认值：30。非必须。  
dns_ttl 30  

\#TAG:route 非必须。  
\#设置VPN路由，符合该路由的网络都会通过VPN。默认值：0.0.0.0/0。非必须。  
route 0.0.0.0/0  

\#TAG:proxy  
\#目前支持HTTP(CONNECT)和Shadowsocks(table加密)两种代理。必须。  
\#可以设置多个代理，但是目前系统只会使用第一个。    

\#需要用户名密码验证的代理服务器地址  
proxy http://username:password@hostname:port  

\#无需验证的代理服务器  
proxy http://hostname:port   

\#shadowsocks地址（目前method仅支持table）  
proxy ss://method:password@hostname:port  

\#Base64加密的shadowsocks地址（目前method仅支持table）  
proxy ss://YmYtY2ZiOnRlc3RAMTkyLjE2OC4xMDAuMTo4ODg4  

\#TAG:outside_china_use_proxy  
\#设置国外网站是否走代理。默认值：on。非必须。  
outside_china_use_proxy on  

\#TAG:direct_domain  
\#设置直连的域名。非必须。  
direct_domain baidu.com qq.com taobao.com  
direct_domain sina.com 163.com sohu.com  

\#TAG:proxy_domain  
\#设置需要代理的域名。非必须。  
proxy_domain google.com twitter.com facebook.com youtube.com  

\#end of file  
