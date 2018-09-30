## ビルド
```
$ docker build -t hello-container .
```

## Container Registryにプッシュ
```
$ docker tag hello-container asia.gcr.io/[YOUR_PROJECT_ID]/helloworld
```
```
$ gcloud docker push asia.gcr.io/[YOUR_PROJECT_ID]/helloworld
```
## クラスタの作成
```
$ $ gcloud container clusters create helloworld --zone asia-northeast1-c \
  --scopes cloud-platform \
  --num-nodes 2
```
## クラスタの認証
```
$ gcloud container clusters get-credentials helloworld --zone asia-northeast1-c
```

## デプロイ
```
$ kubectl create -f deployment.yaml
$ kubectl create -f service.yaml
```

## LoadBalancer IngressのIP確認後アクセス
```
$ kubectl describe service helloworld
```
