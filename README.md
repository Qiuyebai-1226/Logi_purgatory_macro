# Logi_purgatory_macro
罗技G系列炼狱宏 

## 特色 

使用Box-Muller变换生成服从正态分布的随机数，数据真实自然更符合普通人类(~~bushi~~)

## 该代码使用GPL v3.0协议，如需商用，请务必开源并沿用该协议！！

### 2023.8.29

# One More thing

在群友们的建议下做了更好的付费版本，使用体验和稳定程度遥遥领先

### 2023.9.14

数据加强为满速版本，人机不黑屋

[点此查看功能特色](http://120.27.142.252:8848/version/history)

[点此查看教程](http://120.27.142.252:8848/instruction)

___

### 2023.8.24 
某些无良商家，倒卖代码就算了(毕竟是开源免费的)，怎么还敢说自己是全网首发呢？

<img src="https://github.com/Afool4U/Logi_purgatory_macro/assets/83582188/39ae442e-225e-4969-9701-5ecb49808cb1" width="50%">

### 游戏内设置

如需直接使用鼠标左键（而不是侧键）速点，请修改代码中的purgatory_key为1，并执行下面操作：

游戏内设置----控制----战斗操作----射击----按下键盘的“L键”----确定

（不再需要时请改回，否则鼠标左键将无法射击）以下是改回方法：

游戏内设置----控制----战斗操作----射击----单击鼠标左键----确定

原理：当鼠标左键按下时，宏会自动按照速点频率模拟按下键盘上的“L键”，此时将游戏中的开火键改为“L键”即可实现速点。

根本原因：对于任意一个按键来说，它不能既是控制宏的按钮，又是宏要控制的按钮（不信可以试试后果^_^）

### 疑难杂症

1.宏已经配置成功，但游戏内外都没效果

解决方案： 

关闭板载内存模式（原因：板载内存过于隐蔽，所以罗技关掉了宏放入板载的功能）

2.游戏里没有效果（或枪管就转一下），而游戏外正常
   
解决方案： 

右键桌面黑色驱动/蓝色驱动快捷方式点击属性----上方选择兼容性----下方勾选以管理员模式运行此程序----应用----确定

3.出现18行(或其他行)报错：SYNTAX_ERROR Line Number:18

解决方案：

*请使用[此版本代码](%E6%97%A0%E6%B3%A8%E9%87%8A%E7%89%88%E6%9C%AC.lua)。*

### 讲解视频
*点击[此处](https://b23.tv/NYTZymS)查看。*

### 注意事项

不要拿来打人机和排位！！不要拿来打人机和排位！！不要拿来打人机和排位！！

默认是滚轮中键单击 开启/关闭 宏

鼠标左侧离鼠尾近的一端 是速点键

(无侧键的鼠标请查看代码提示进行改键)

使用之前请先看代码，并配置相关数据。

出现问题请多看文档！！（免费的还要什么自行车^_^）

### 讨论Q群

群号：702325640

群文件有视频讲解、鼠标键位大全和宏代码文件。请谨慎使用其他群员上传的文件，出现问题概不负责！！

### 版本更新

#### 2023.8.25
- 使用更科学的时间作为随机数种子（利用GetDate）
- 使用精确延时函数（感谢[@CHN-FengGe](https://github.com/CHN-FengGe)的[代码](https://github.com/CHN-FengGe/PUBG/blob/main/PUBG_FengGe_FIX_230625.lua)提供思路）

#### 2023.8.26

- 删除精确延时函数(电脑性能不足时会导致卡顿)

### 福利

目前市面上很多宏需要定时更新。实际上，这些宏都只是做了时间判断，新版的内容根本毫无修改，严重损害消费者的权益。

破解方法(无论代码是否加密)：在你的宏文件第一行最前按回车新开一行，然后粘贴进去如下代码：

```lua
function GetDate(...)
  return ""
end
```

解释：罗技取时间的方法非常唯一，只能使用官方提供的GetDate函数。

既然如此，只需重写一下GetDate函数，返回一个空字符串就行了。

原理很简单，空字符串比所有字符串(时间)都小，那么自然会误认为当前时间在有效期之前。
