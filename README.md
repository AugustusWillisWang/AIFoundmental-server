# AIFoundmental-server

Server design and document for AIFoundmental course 149543.

<!-- TOC -->

- [AIFoundmental-server](#aifoundmental-server)
    - [1.1. 综述](#11-综述)
    - [1.2. Stage 1](#12-stage-1)
    - [1.3. Stage 2](#13-stage-2)
    - [1.4. Stage 3](#14-stage-3)
    - [1.5. 目前的软件配置](#15-目前的软件配置)
    - [1.6. 服务器IP地址](#16-服务器ip地址)
    - [1.7. 实现相关](#17-实现相关)

<!-- /TOC -->

## 1.1. 综述

本次课程服务器使用共分成三个阶段. 

因为整体上看服务器资源比较充足, 同时使用一台服务器的小组数量较少, 所以服务器的分配采用"自行协调为主, 冲突处理手段为辅的方式".

<!-- 用户账号没有软件安装权限, 由管理员安装软件. -->

## 1.2. Stage 1

第一阶段, 使用公共账号登录服务器, 熟悉服务器的使用. 尝试在服务器上上传并运行自己的任务.

这一阶段全班使用统一的公共账号`pubuser`.

公共账号密码为`TODO`. (见课程群)

第一阶段有四台服务器, 建议在一台服务器有负载的时候尝试使用其他的服务器.

## 1.3. Stage 2

在分组完成之后进入第二阶段.

在此阶段中, 每个小组会被分配到一台固定的服务器, 在这台服务器上使用小组账号进行操作.

在管理程序上线之前, 暂时使用 github 上此项目下 `/服务器号.md` 来登记使用情况. 请需要长时间使用服务器的小组修改此文件并`push`, 发起 `merge` 申请. 管理员 `merge` 修改到主分支之后代表预约成功.

请在务必在长时间占用GPU之前进行预约. 如果出现未预约组长时间占用GPU的情况, 请联系管理员(联系方式: TODO)进行处理.

## 1.4. Stage 3

在大作业进行到需要服务器进行较长时间的运算的时候进入第三阶段.

在默认情况下, 对于服务器的使用不做限制. 此阶段下登陆时会有当前服务器使用情况提示. 不同小组需要同时用到服务器时, 可以先尝试自行沟通来解决资源分配的问题.

请注意尽量不要影响到其他组的工作, 比如未经沟通长时间占用服务器及长时间占用GPU.

在此阶段中, 为了解决冲突, 可以使用以下命令来停止GPU运行并申请独占服务器:

```
/opt/require_server 小时数
```

在此期间一个小组可以独占此服务器上的GPU. 

每个小组可以独占服务器的时间是有限的, 在布置任务每个小组都会被分配到相同的独占时间. 

在任务接近提交的阶段, 为了防止大家集中在此阶段集中使用服务器, 规定最大剩余独占时间不超过`剩余时间/剩余小组数`.

**请务必尽早使用服务器**

## 1.5. 目前的软件配置

CUDA
anaconda(python2.7+tensorflow)

## 1.6. 服务器IP地址

```
TODO
TODO
```

## 1.7. 实现相关
<!-- 
scp C:\Users\autum\download2\Anaconda2-5.3.0-Linux-x86_64.sh root@124.16.70.64:/home/tmp_setupenv
yum

groupadd student

add_student()
{
    echo $1
    sudo useradd -c "Student account for $1" -d /home/student/$1 -m $1 -g student 
    passwd -d $1
    passwd -f $1
} -->
```

使用crontab来进行时间管理.

批量操作 ref: http://www.runoob.com/linux/linux-user-manage.html

crontab: http://www.runoob.com/w3cnote/linux-crontab-tasks.html

+

shell ref: https://zhidao.baidu.com/question/2118024779094212987.html

use w to see current Users

grep + w + crontab + shell


crontab -e
counter:
*/5 * * * * ./count_time.sh

每条任务调度执行完毕，系统都会将任务输出信息通过电子邮件的形式发送给当前系统用户，这样日积月累，日志信息会非常大，可能会影响系统的正常运行，因此，将每条任务进行重定向处理非常重要。 例如，可以在crontab文件中设置如下形式，忽略日志输出:

0 */3 * * * /usr/local/apache2/apachectl restart >/dev/null 2>&1

add:
30 21 * * * logout >/dev/null 2>&1
(logout in 21:30)
```

***

如有任何问题, 请在课程群中联系管理员或者在此项目下提交 issue.

管理员联系方式: TODO