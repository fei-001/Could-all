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

```shell
cd springcloud
rm -rf .git
```

![image](https://github.com/user-attachments/assets/ff5e22ce-62bc-4702-8a9f-b4ab6ead3199)

![image-20241124185403049](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124185403049.png)

## 刷新gitlab`(可以看出文件上传成功)`

![image-20241124185501790](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124185501790.png)

## 开始写流水线

![image-20241124185724253](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124185724253.png)

[^上图，图片上的勾上]: 

![image-20241124185943472](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124185943472.png)

### 生成流水线脚本

![image-20241124190145370](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124190145370.png)

![image-20241124190254337](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124190254337.png)

![image-20241124190326931](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124190326931.png)

![image-20241124190409827](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124190409827.png)

## 开始搓流水线

```shell
node{
    stage("pull code"){
        git branch: 'main', credentialsId: '519c7390-1717-454f-8ee3-de8b1d00c76e', url: 'http://192.168.200.30:30888/root/springcloud'
    }
    stage("maven build"){
        sh '''/var/jenkins_home/apache-maven-3.6.3/bin/mvn package -DskipTests -f /var/jenkins_home/workspace/springcloud'''
    }
    stage("docker build"){
        sh '''docker build -t 192.168.200.30/springcloud/sqshq/piggymetrics-config -f config/Dockerfile config'''
        sh '''docker build -t 192.168.200.30/springcloud/sqshq/piggymetrics-gateway -f gateway/Dockerfile gateway'''
    }
    stage("deploy"){
        sh '''sed -i "s%sqshq/piggymetrics-config%192.168.200.30/springcloud/sqshq/piggymetrics-config%g" yaml/svc/config-svc.yaml'''
        sh '''sed -i "s%sqshq/piggymetrics-gateway%192.168.200.30/springcloud/sqshq/piggymetrics-gateway%g" yaml/svc/gateway-svc.yaml'''
        sh '''kubectl create ns springcloud'''
        sh '''kubectl apply -f yaml/deployment/config-deployment.yaml'''
        sh '''kubectl apply -f yaml/deployment/gateway-deployment.yaml'''
        sh '''kubectl apply -f yaml/svc/config-svc.yaml'''
        sh '''kubectl apply -f yaml/svc/gateway-svc.yaml'''
    }
}
```

![image-20241124192122991](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124192122991.png)

> 第二步保存原因没有docker加载镜像，解决如下：

![image-20241124192023107](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124192023107.png)

![image-20241124194234479](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124194234479.png)

```shell
chmod -R 777 /var/run/docker.sock  # 加权限
```

![image-20241124200855109](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124200855109.png)

# 给空间加权限

```shell
kubectl create clusterrolebinding jenkins-cluster-admin \
--clusterrole=cluster-admin \
--serviceaccount =default:default
kubectl create serviceaccouni jenkins-sa 
kubectl create clusterrolebinding jenkins-sa-cluster-admin \
--clusterrole=cluster-admin \
--serviceaccount=default:jenkis-sa
```

![image-20241124201011332](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241124201011332.png)

# 两种方法

## 1.使用本地镜像

```shell
 docker save -o hua.tar 192.168.200.30/springcloud/sqshq/piggymetrics-config
 docker save -o li.tar 192.168.200.30/springcloud/sqshq/piggymetrics-gateway
 ctr -n k8s.io images import li.tar         
 ctr -n k8s.io images import hua.tar   
```

## 2.从harbor仓库拉

```shell
node{
    stage("pull code"){
        git branch: 'main', credentialsId: '519c7390-1717-454f-8ee3-de8b1d00c76e', url: 'http://192.168.200.30:30888/root/springcloud'
    }
    stage("maven build"){
        sh '''/var/jenkins_home/apache-maven-3.6.3/bin/mvn package -DskipTests -f /var/jenkins_home/workspace/springcloud'''
    }
    stage("docker build"){
        sh '''docker build -t 192.168.200.30/springcloud/sqshq/piggymetrics-config -f config/Dockerfile config'''
        sh '''docker build -t 192.168.200.30/springcloud/sqshq/piggymetrics-gateway -f gateway/Dockerfile gateway'''
    }
    stage("docker pull"){
       sh '''docker login -uroot -padmin12345'''
       sh '''docker pull 192.168.200.30/springcloud/sqshq/piggymetrics-config'''
       sh '''docker pull 192.168.200.30/springcloud/sqshq/piggymetrics-gateway'''
    }
    stage("deploy"){
        sh '''sed -i "s%sqshq/piggymetrics-config%192.168.200.30/springcloud/sqshq/piggymetrics-config%g" yaml/svc/config-svc.yaml'''
        sh '''sed -i "s%sqshq/piggymetrics-gateway%192.168.200.30/springcloud/sqshq/piggymetrics-gateway%g" yaml/svc/gateway-svc.yaml'''
        sh '''kubectl create ns springcloud'''
        sh '''kubectl apply -f yaml/deployment/config-deployment.yaml'''
        sh '''kubectl apply -f yaml/deployment/gateway-deployment.yaml'''
        sh '''kubectl apply -f yaml/svc/config-svc.yaml'''
        sh '''kubectl apply -f yaml/svc/gateway-svc.yaml'''
    }
}

```

## 改harbor配置文件（vi /etc/containerd/config.toml ）

![微信图片_20241123161055](E:\this\Desktop\微信图片_20241123161055.jpg)