## 一、说明

每个carbon产品的用户界面允许您配置、监控、调整和维护产品。 的组件制定这些用户界面的设计和风格在资源(jar)文件中定义。

每一个carbon产品的用户界面由两层组成:

- 常见的产品布局/设计继承了carbon平台:所有常见的模板,风格(CSS文件),和图像存储在carbon核心UI包,命名`org.wso2.carbon.ui-<version-number>.jar`(`<version-number>`是包的特定版本)。 这个包是负责整个carbon平台的整体外观和感觉。
- 每个产品特有的风格/图片:每个carbon产品(即建立在carbon内核)还有另一个风格包,其中包含所有最重要的样式表和图片:`org.wso2.<product-name>.styles-<version-number>.jar`。

您可以定制用户界面通过修改这些资源文件。 您需要创建一个片段为原始资源文件包。 然后,您可以把修改资源文件中所需的包。 文件所需的包将会得到优先级和将会覆盖在原来的文件包。

你可以使用相同的技术来定制用户界面的任何方面。 这种技术的优点是,你不会失去你的定制应用官方补丁的产品替换原有的包。

## 二、参考

详细说明请参考:[Customizing+the+Management+Console](https://docs.wso2.com/display/ADMIN44x/Customizing+the+Management+Console)

## 三、如何使用该项目来自定义IS的管理控制台？

1、构建这个项目。

> 打开终端,导航到相关项目目录(上述),并执行下面的命令:
>
> ```
> mvn clean install
> ```
>
> 这个项目包含两个模块：
>
> ```
> org.wso2.carbon.ui_4.4.35_fragment
> org.wso2.carbon.ui_4.4.35_patch
> ```
>
> 项目构建成功后，会分别在上述两个模块的target目录下各生成一个jar文件。
>
> ```
> org.wso2.carbon.ui_4.4.35_fragment-1.0.0.jar
> org.wso2.carbon.ui_4.4.35_patch-1.0.0.jar
> ```

2、复制上面两个jar文件到下面的目录中

```
<PRODUCT_HOME>/repository/components/dropins/
```

3、重新启动WSO2产品服务器。

