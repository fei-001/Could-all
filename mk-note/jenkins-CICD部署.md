# jenkins-CICD部署

## 1.准备阶段

> 上传Jenkins-exam.tar.gz

![image-20241123183834478](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123183834478.png)

## 2.部署gitlab和jenkins

```shell
kubectl apply -f gitlab.yaml
kubectl apply -f jenkins.yaml
```

![image-20241123184336246](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123184336246.png)

## 3.获取jenkins密码

![image-20241123185804167](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123185804167.png)

> ``需要用红色路径去容器里面来获取密码``

![image-20241123190030397](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123190030397.png)

```shell
kubectl get po   #获取pod
kubectl exec -it jenkins-59bd8bcb64-jv2qs bash
```

![image-20241123190217805](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123190217805.png)

## 4.图形化操作

![image-20241123190612309](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123190612309.png)

![image-20241123190717749](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123190717749.png)

![image-20241123190842513](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123190842513.png)

>### `因为重启所以需要重新获取密码`

![image-20241123191255020](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123191255020.png)

### 创建新用户

![image-20241123191426995](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123191426995.png)

![image-20241123191507771](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123191507771.png)

### 然后注销用新用户登录.........

## 5.备用

![image-20241123191812615](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123191812615.png)

![image-20241123192157854](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123192157854.png)

![image-20241123192358749](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123192358749.png)

## 6.Maven操作

![image-20241123192959276](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123192959276.png)

![image-20241123193325117](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123193325117.png)

​              然后保存

## 7.登录gitlab

> user：root
>
> password:admin123

## 8.获取token

![image-20241123193637440](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123193637440.png)

![image-20241123193712122](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123193712122.png)

![image-20241123193804037](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123193804037.png)

![image-20241123193855165](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123193855165.png)



#### jenkins操作

![image-20241123194443181](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123194443181.png)

![image-20241123194127448](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123194127448.png)

![image-20241123194324790](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123194324790.png)

### gitlab操作

新建项目

![image-20241123194732500](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123194732500.png)

![image-20241123194756932](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123194756932.png)

![image-20241123194830509](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123194830509.png)

`接下来回到命令行`

![image-20241123195009849](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123195009849.png)

![image-20241123195117246](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241123195117246.png)