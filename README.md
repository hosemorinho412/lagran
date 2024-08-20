- 本小程序主要用来实现Geneva的以下四条规则，还可以自定义端口、需要修改的window size的值。
```
"[TCP:flags:SA]-tamper{TCP:window:replace:0}-|"
"[TCP:flags:A]-tamper{TCP:window:replace:0}-|"
"[TCP:flags:PA]-tamper{TCP:window:replace:0}-|"
"[TCP:flags:FA]-tamper{TCP:window:replace:0}-|"
```
四条规则全部开启，端口80和443：

```
./lagran -p 80,443 -daemon -forever
```

开启第1、2条规则，关闭第3、4条规则，并把第1条规则的window size改为2,第2条规则的window size改为3，端口80和443：

```
./lagran -p 80,443 -sa=true -wsa 2 -a=true -wa 3 -pa=false -fa=false -daemon -forever
```


```
./lagran -p 80,443 -sa=true -wsa 17 -a=true -wa 17 -pa=true -wpa 17 -fa=true -wfa 17
```
