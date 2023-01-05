# oe_test_docker_port_mapping_001

## 描述

registry镜像端口映射

## 预置条件

1.安装docker并拉去镜像

```yum install -y  docker
docker pull busybox
```

## 测试步骤

1.创建容器

```docker run --name=container_registry -d -P registry
```

2.查询映射的主机端口

```docker port container_registry
```

3.指定映射端口

```docker run --name=container_registry -d -p 5000:5000 registry
```

4.查询指定端口

```docker port container_registry
```

## 预期结果

1.创建成功

2.查询到端口

3.指定端口成功

4.查询出的端口为指定的5000

## 备注