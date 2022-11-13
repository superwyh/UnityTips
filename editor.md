# Unity开发技巧：编辑器

### 在代码里组织Inspector的信息

```csharp
[Header("移动速度")]
public float speed;
```
增加一个标题，效果如下：
![Header](images/ab109ba753e2f9d573d8a67a95b280a4a5c024a85b7db660c9f05e1cdfeaba0c.png)  

```csharp
[Tooltip("移动速度，浮点类型")]
public float speed;
```
增加一个鼠标指向的提示，效果如下：
![Tooltip](images/f42f00f5f0bc23b0eb159c8176ea001ca9985add93045fe5112752220d84cfb3.png)  

```csharp
public float speed;
[Space(50)]
public Transform target;
```
增加空行，数字为空行宽度，效果如下：
![Space](images/de771a4cc134172ab0c64d56bdd706e1fc17ea33fcda59c7daed40e81ed9a4fb.png)  
