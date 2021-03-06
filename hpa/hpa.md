horizontal Pod Autoscaling可以根据CPU使用率或应用自定义metrics自动扩展Pod数量（支持replication controller、deployment和replica set）。

* 控制管理器每隔30s（可以通过–horizontal-pod-autoscaler-sync-period修改）查询metrics的资源使用情况

支持三种metrics类型

* 预定义metrics（比如Pod的CPU）以利用率的方式计算
* 自定义的Pod metrics，以原始值（raw value）的方式计算
* 自定义的object metrics

* 支持两种metrics查询方式：Heapster和自定义的REST API
* 支持多metrics


自定义metrics
使用方法

+ 控制管理器开启–horizontal-pod-autoscaler-use-rest-clients
+ 控制管理器的–apiserver指向API Server Aggregator
+ 在API Server Aggregator中注册自定义的metrics API

