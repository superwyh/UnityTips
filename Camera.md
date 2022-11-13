# Unity开发技巧：摄像机的操作

### 屏幕坐标转世界坐标

```Csharp
transform.position = new Vector2(Camera.main.ScreenToWorldPoint(Input.mousePosition).x,Camera.main.ScreenToWorldPoint(Input.mousePosition).y);
```
