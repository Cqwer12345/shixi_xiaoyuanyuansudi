<img width="1317" height="639" alt="image" src="https://github.com/user-attachments/assets/357b0f9c-f77c-4088-8192-5c681b438c82" />一、项目介绍以及环境搭建
1.苍穹外卖项目介绍
1.1项目介绍
本项目（苍穹外卖）是专门为餐饮企业（餐厅、饭店）定制的一款软件产品，包括 系统管理后台 和 小程序端应用 两部分。其中系统管理后台主要提供给餐饮企业内部员工使用，可以对餐厅的分类、菜品、套餐、订单、员工等进行管理维护，对餐厅的各类数据进行统计，同时也可进行来单语音播报功能。小程序端主要提供给消费者使用，可以在线浏览菜品、添加购物车、下单、支付、催单等。
<img width="1008" height="397" alt="image" src="https://github.com/user-attachments/assets/abaeae55-7510-4240-9b99-6e213b809fac" />
接下来，通过功能架构图来展示管理端和用户端的具体业务功能模块。
<img width="695" height="422" alt="image" src="https://github.com/user-attachments/assets/46c0d952-d23b-4c13-8128-e53bfd0ab2db" />
<img width="695" height="422" alt="image" src="https://github.com/user-attachments/assets/d00347ea-1ad7-4185-9ebe-241677edc233" />
1). 管理端功能
员工登录/退出 , 员工信息管理 , 分类管理 , 菜品管理 , 套餐管理 , 菜品口味管理 , 订单管理 ，数据统计，来单提醒。
2). 用户端功能
微信登录 , 收件人地址管理 , 用户历史订单查询 , 菜品规格查询 , 购物车功能 , 下单 , 支付、分类及菜品浏览。

1.2产品原型
产品原型，用于展示项目的业务功能，一般由产品经理进行设计。
注意事项： 产品原型主要用于展示项目的功能，并不是最终的页面效果。
管理端原型图：<img width="1317" height="639" alt="image" src="https://github.com/user-attachments/assets/f2d32635-cde7-43e8-be5b-55d1e852b7e9" />
用户端原型图：<img width="977" height="647" alt="image" src="https://github.com/user-attachments/assets/63af62f7-53be-4281-857d-009cb8a4c6dd" />
1). 管理端
餐饮企业内部员工使用。 主要功能有:

模块	描述
登录/退出	内部员工必须登录后,才可以访问系统管理后台
员工管理	管理员可以在系统后台对员工信息进行管理，包含查询、新增、编辑、禁用等功能
分类管理	主要对当前餐厅经营的 菜品分类 或 套餐分类 进行管理维护， 包含查询、新增、修改、删除等功能
菜品管理	主要维护各个分类下的菜品信息，包含查询、新增、修改、删除、启售、停售等功能
套餐管理	主要维护当前餐厅中的套餐信息，包含查询、新增、修改、删除、启售、停售等功能
订单管理	主要维护用户在移动端下的订单信息，包含查询、取消、派送、完成，以及订单报表下载等功能
数据统计	主要完成对餐厅的各类数据统计，如营业额、用户数量、订单等
2). 用户端
移动端应用主要提供给消费者使用。主要功能有:

模块	描述
登录/退出	用户需要通过微信授权后登录使用小程序进行点餐
点餐-菜单	在点餐界面需要展示出菜品分类/套餐分类, 并根据当前选择的分类加载其中的菜品信息, 供用户查询选择
点餐-购物车	用户选中的菜品就会加入用户的购物车, 主要包含 查询购物车、加入购物车、删除购物车、清空购物车等功能
订单支付	用户选完菜品/套餐后, 可以对购物车菜品进行结算支付, 这时就需要进行订单的支付
个人信息	在个人中心页面中会展示当前用户的基本信息, 用户可以管理收货地址, 也可以查询历史订单数据

1.3 技术选型
关于本项目的技术选型, 我们将会从 用户层、网关层、应用层、数据层 这几个方面进行介绍，主要用于展示项目中使用到的技术框架和中间件等。
<img width="1097" height="416" alt="image" src="https://github.com/user-attachments/assets/a6e05ef3-9093-470f-b345-16f8b0ffe815" />
1). 用户层
本项目中在构建系统管理后台的前端页面，我们会用到H5、Vue.js、ElementUI、apache echarts(展示图表)等技术。而在构建移动端应用时，我们会使用到微信小程序。
2). 网关层
Nginx是一个服务器，主要用来作为Http服务器，部署静态资源，访问性能高。在Nginx中还有两个比较重要的作用： 反向代理和负载均衡， 在进行项目部署时，要实现Tomcat的负载均衡，就可以通过Nginx来实现。
3). 应用层
SpringBoot： 快速构建Spring项目, 采用 “约定优于配置” 的思想, 简化Spring项目的配置开发。
SpringMVC：SpringMVC是spring框架的一个模块，springmvc和spring无需通过中间整合层进行整合，可以无缝集成。
Spring Task: 由Spring提供的定时任务框架。
httpclient: 主要实现了对http请求的发送。
Spring Cache: 由Spring提供的数据缓存框架
JWT: 用于对应用程序上的用户进行身份验证的标记。
阿里云OSS: 对象存储服务，在项目中主要存储文件，如图片等。
Swagger： 可以自动的帮助开发人员生成接口文档，并对接口进行测试。
POI: 封装了对Excel表格的常用操作。
WebSocket: 一种通信网络协议，使客户端和服务器之间的数据交换更加简单，用于项目的来单、催单功能实现。
4). 数据层
MySQL： 关系型数据库, 本项目的核心业务数据都会采用MySQL进行存储。
Redis： 基于key-value格式存储的内存数据库, 访问速度快, 经常使用它做缓存。
Mybatis： 本项目持久层将会使用Mybatis开发。
pagehelper: 分页插件。
spring data redis: 简化java代码操作Redis的API。
5). 工具
git: 版本控制工具, 在团队协作中, 使用该工具对项目中的代码进行管理。
maven: 项目构建工具。
junit：单元测试工具，开发人员功能实现完毕后，需要通过junit对功能进行单元测试。
postman: 接口测工具，模拟用户发起的各类HTTP请求，获取对应的响应结果。
2.开发环境搭建
<img width="855" height="398" alt="image" src="https://github.com/user-attachments/assets/2dfe216a-da05-4f92-8831-4d7e885d7c9b" />
开发环境搭建主要包含前端环境和后端环境两部分。作为服务端开发工程师， 我们课程学习的重心应该放在后端的业务代码上， 前端的页面我们只需要导入资料中的nginx， 前端页面的代码我们只需要能看懂即可。

2.1 前端环境搭建
1). 前端工程基于 nginx
从资料中找到前端运行环境的nginx，移动到非中文目录下。
<img width="1704" height="470" alt="image" src="https://github.com/user-attachments/assets/99ac525f-89d8-49b1-addf-1a33765b1188" />
sky目录中存放了管理端的前端资源，具体如下：
<img width="1032" height="603" alt="image" src="https://github.com/user-attachments/assets/fef72827-b918-46c0-88b1-20846d722034" />
2). 启动nginx，访问测试
双击 nginx.exe 即可启动 nginx 服务，访问端口号为 80
http://localhost:80
<img width="1287" height="686" alt="image" src="https://github.com/user-attachments/assets/168afbfc-2137-4df8-8fcb-0fed13d7b720" />
但是为了比较端口冲突，我们可以把端口进行修改
<img width="1747" height="1065" alt="image" src="https://github.com/user-attachments/assets/6be5fdcc-1f75-461d-a947-6c3cbed6d56a" />
2.2后端环境搭建
2.2.1 熟悉项目结构
后端工程基于 maven 进行项目构建，并且进行分模块开发。
1). 从资料中找到后端初始工程：
<img width="954" height="275" alt="image" src="https://github.com/user-attachments/assets/69fd1188-2d7a-4301-9aee-0f8dd7b977fa" />
2). 用 IDEA 打开初始工程，了解项目的整体结构：
<img width="675" height="677" alt="image" src="https://github.com/user-attachments/assets/7b65fd2f-a389-4d90-864f-4c35e6c49ab2" />
对工程的每个模块作用说明：

序号	名称	说明
1	sky-take-out	maven父工程，统一管理依赖版本，聚合其他子模块
2	sky-common	子模块，存放公共类，例如：工具类、常量类、异常类等
3	sky-pojo	子模块，存放实体类、VO、DTO等
4	sky-server	子模块，后端服务，存放配置文件、Controller、Service、Mapper等
对项目整体结构了解后，接下来我们详细分析上述的每个子模块：

sky-common: 模块中存放的是一些公共类，可以供其他模块使用
<img width="617" height="663" alt="image" src="https://github.com/user-attachments/assets/93c18703-24e3-4d9b-ac86-e2da23503638" />
分析sky-common模块的每个包的作用：



苍穹外卖——员工管理，分类管理
内容
新增员工(重点)
员工分页查询(重点)
启用禁用员工账号
编辑员工(重点)
导入分类模块功能代码
**功能实现：**员工管理、菜品分类管理。
员工管理效果：
<img width="1613" height="763" alt="image" src="https://github.com/user-attachments/assets/72e02755-063b-4e1c-9fa4-d661f40ac83f" />
菜品分类管理效果：
<img width="1344" height="636" alt="image" src="https://github.com/user-attachments/assets/dc364491-8c4a-4b09-ab7c-99dd7e8ee05c" />


