
```shell
~ kustomize build base

apiVersion: apps/v1
kind: Deployment
metadata:
  name: deploy
spec:
  template:
    metadata:
      labels:
        foo: bar
    spec:
      containers:
      - args:
        - one
        - two
        image: nginx
        name: nginx
```


```shell
~ kustomize build eu-west-1/dev

apiVersion: apps/v1
kind: Deployment
metadata:
  name: deploy
spec:
  template:
    metadata:
      labels:
        foo: bar
    spec:
      containers:
      - args:
        - one
        - two
        image: nginx:latest
        name: nginx
```

```shell
~ kustomize build eu-west-1/prod

apiVersion: apps/v1
kind: Deployment
metadata:
  name: deploy
spec:
  template:
    metadata:
      labels:
        foo: bar
    spec:
      containers:
      - args:
        - one
        - two
        image: nginx:stable
        name: nginx
```