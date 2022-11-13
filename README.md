# Unity开发技巧(施工中)

---
## 常用快捷键

### QWERTY

![QWERTY](images/dbea150663a9c28333a79772240a3242caaac7f019dce21a5e12e537a714d75d.png)  

这六个常用操作，对应的快捷键分别是 QWERTY。

### 查找或自定义快捷键

Unity支持自定义快捷键，地址如下：

```
Windows: Edit -> Shortcuts
Mac: Unity -> Shortcuts
```

在这里也可以查找快捷键，界面如下：

![Shortcuts](images/89697c39bed2ac71f00374467b41387c5d622232a868eaf75dd4d16db48741f2.png)  


### 展开或收起所有层级

假设你的 Hierarchy 窗口里的东西层级非常多，想要一次性收起或者打开所有层级的子物体。只需要按住ALT键点击 GameObject 左边的小三角就可以。

---

## 摄像机操作

### 屏幕坐标转世界坐标

```csharp
transform.position = new Vector2(Camera.main.ScreenToWorldPoint(Input.mousePosition).x,Camera.main.ScreenToWorldPoint(Input.mousePosition).y);
```

---

## 按键相关

### 获取正在按下的键
```csharp
if (Input.anyKeyDown) 
    {
        foreach (KeyCode keyCode in Enum.GetValues(typeof(KeyCode)))
        {
            if (Input.GetKeyDown(keyCode))
            {
                //keyCode就是正在按下的键
            }
        }
    }
```

---

## 运行环境

### 运行模式着色

Unity默认在运行模式下，场景内的操作是不会保留的，所以很容易出现开发者没注意是运行模式，进行了修改，结果没有保存的情况。那么可以使用运行模式着色，提醒开发者正在运行模式内。设置地址如下：

```
Windows: Edit -> Preference -> Colors -> Playmode tint
Mac: Unity -> Preference-> Colors -> Playmode tint
```

![Playmode tint](images/13a0d8cc53e7562f8bfdeba84e648d9d164f919b77bc34b8a7b3220f30c8f5e8.png)  

只需要修改这里的颜色后，在运行模式时，窗口就会被加上颜色，如下：

![上色后](images/20db41fcfacefa81417f06dc44c798a0e66d17c6969543fce3742b716a4c401c.png)  

### 运行模式下改动

假如你也根本没有注意到运行模式的着色，还是修改了内容，也有办法保存。

### 使用Debug.log 的第二个参数，实现调试时定位到GameObject

我们调试时，有可能会遇到一堆Debug.log的信息，只需要加入第二个参数，在Console窗口里直接点击这条信息，就可以自动定位到对应的GameObject。

```csharp 
Debug.Log("试试这个", this.gameObject);
```
### 使用Debug.Break()暂停调试

在代码里使用Debug.Break()直接在所在位置暂停。

---

## 编辑器

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



