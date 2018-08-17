# project-deploy
利用gitlab-ci 、helm 部署应用到kubernetes

# deploy.sh 把所有发布的项目批量写入
```
$ cd ./k8s
$ ls -l |awk -F" " '{print "#deploy ",$9}'
```

# destroy.sh 把所有删除的项目批量写入
```
$ cd ./k8s
$ ls */chart/*-value* -l |awk -F " " '{print $9}' |awk -F "/" '{print $3}' |awk -F "-values.yaml" '{print "#destroy ",$1}'
```
