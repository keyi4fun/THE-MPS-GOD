# THE-MPS-GOD

**在阅读之前，请各位：感恩🙏🙏🙏🙏**

**墨门🙏🙏🙏🙏**

**🙏🙏🙏🙏🙏🙏🙏🙏 蘑菇蓝先生维护好几个服务端还负债累累，依然夜以继日精益求精废寝忘食的给我们带来全球首款多线程重写版高并发服务端：MPS 🙏🙏🙏🙏🙏🙏🙏🙏**

**墨老如此努力工作，你怎么能诋毁他！！！没有他，你怎么开得了服务器！！！！**

**让我们再次感恩：墨门🙏🙏🙏🙏**

**本文不做任何排版，若您感到不舒服请停止阅读。**

## 起因

2023 年 3 月, Mohist 开发组宣布了全球首款重写版多线程高并发核心：MPS。

*以下为当时 "核心文档页" 的截图归档，该页面在 MPS 真正发布的时候已经被修改去除了造假图片，后文会提到。*

![QQ图片20230416123746](https://user-images.githubusercontent.com/53771072/232273118-18bfc820-8044-4cdd-9cb4-32d471647616.jpg)

在本页面中，我们可以清楚的看到 MPS-Dev-0748 与 Paper 的对比：

![image](https://user-images.githubusercontent.com/53771072/232273239-f1662eca-e46f-493a-96ef-635c2edffe43.png)

![image](https://user-images.githubusercontent.com/53771072/232273247-e8ca07b1-3641-4aa5-97bd-5e3c3fd59523.png)

如果您仔细观察，您可以发现所谓 MPS 截图中，村民的位置很明显不对劲：

![image](https://user-images.githubusercontent.com/53771072/232273265-bc9fdec7-51fc-4302-8d41-b577028e055f.png)

他们统统朝向一个方向。

并且：

![image](https://user-images.githubusercontent.com/53771072/232273272-0eeb9b20-bf3e-49e8-b8c8-cea63e728fc6.png)

究竟是什么黑魔法，能让一个区域里塞入 6k+ 村民还不被挤压分散开？

实现方法很简单，在 Minecraft 服务端中有一个 `entityList` 变量来存储所有的实体。

我们只需要：

```java
entityList.forEach(entity -> {
    entity.setAI(false);
});
```

即可实现该效果。

您可能已经意识到了这端代码的作用：关闭生物 AI。
