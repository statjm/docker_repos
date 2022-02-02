# python과 R kernel을 지원하는 Jupyterlab Dockerfile

아나콘다를 설치하고 싶지 않을 때, 그리고 파이썬 가상환경을 쓰는 경우가 별로 없을 때

* 기본이미지 : jupyter/r-notebook
<https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html>

## 이미지 빌드

```shell
sudo docker build -t rupyterlab ./rupyterlabs
```

## 컨테이너 실행

```shell
sudo docker run -d --restart always -p 8888:8888 -v e:/workspace/rupyterlab:/home/jovyan --name rupyterlab -e JUPYTER_ENABLE_LAB=yes -e GRANT_SUDO=yes -e JUPYTER_ALLOW_INSECURE_WRITES=true rupyterlab
```