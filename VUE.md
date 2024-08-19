**VUE framework system has logical defects** and vulnerabilities

Vulnerability description:

Vue.js is a progressive framework for building user interfaces. It is a JavaScript framework used for building user interfaces. As one of the three dominant front-end frameworks (Vue, React, Angular), it is built on standard HTML, CSS, and JavaScript, and provides a declarative, component-based programming model to help you efficiently develop user interfaces. The VUE framework system has a logical vulnerability that attackers can exploit to bypass system authentication and log in to any account.

VUE official website: https://cn.vuejs.org/

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/VUE.png)

Use a network surveying platform to search for and filter icons of VUE framework and JS page prompts for the BODY attribute of VUE framework, For example: fofa（ https://fofa.info/ ） Grammar:

(icon_hash="-1252041730" || icon_hash="1917028407") && body="Please enable it to continue"

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/VUE2.png)

\2. Reproduce the process

IP1: http://dksxbm.axhu.edu.cn/#/

Enter your ID card (username), any password, log in, and use Burp to capture this login

package

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tu1.png)

Log in to the package on the BURP interface, right-click and select the option marked in the image (Do intercept ------- Response to this request), and then send the package.

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tu2.png)

Change the code response value here to 200.

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tu3.png)

Successfully entered the system.

It can be seen that successfully entering the backend, any account can enter the backend without authorization, even if it does not exist, so all usernames can be logged in without authorization.

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tu4.png)

复现 IP2：https://goatmanagementsystem.cn/#/login

Still crawling login packages，Log in to the package on the BURP interface, right-click and select the option marked in the image (Do intercept ------- Response to this request), and then send the package.

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tuu1.png)

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tuu2.png)

Change the code response value here to 200.

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tuu3.png)

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tuu4.png)

复现 IP3：http://124.220.107.171/#/login

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tuuu1.png)

Still crawling login packages，Log in to the package on the BURP interface, right-click and select the option marked in the image (Do intercept ------- Response to this request), and then send the package.

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tuuu2.png)

Change the code response value here to 200.

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tuuu3.png)

复现 IP4：http://120.24.68.3/

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tuuu4.png)

![img](https://github.com/bluewuyan/8.19VUE/blob/main/photo/tu4.png)

Change the code response value here to 200.

![img](file:///C:/Users/26630/AppData/Local/Temp/msohtmlclip1/01/clip_image033.jpg)

Other reproduced IPs: [http://47.103.199.200/login ]

[(http://47.103.199.200/login)

[http://62.234.19.48:9001/ ](http://62.234.19.48:9001/)

[http://60.205.180.60:8077/ ]

[(http://60.205.180.60:8077/)

[https://152.136.36.174:1443/ ]

[(https://152.136.36.174:1443/)

[http://43.143.17.64:10000/ ]

[(http://43.143.17.64:10000/)

http://101.133.135.26/

