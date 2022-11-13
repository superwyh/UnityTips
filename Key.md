# Unity开发技巧：按键相关

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