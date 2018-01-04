# feiyu sdk web demo

* #### 环境要求
> 推荐 Chrome 浏览器: v58 或以上版本

<br>
* #### 创建客户端（Client）对象
使用 FYRtcEngine 对象创建客户端（Client）对象。

```javascript
var client = FYRtcEngine.createClient(options, callbacks);
```

| 参数 | 是否必须 | 描述 |
| ---- | :---- | :---- |
| option | 是 | json对象，包含Client需要的各种参数 |
| callbacks | 否 | json对象，包含Client的各种事件回调 |

示例代码：
```javascript
var client = FYRtcEngine.createClient({
    appId: appId,
    appToken: appToken,
    audioElement: audioElement
}, {
    onJoinChannelSuccess: function () {
        // 加入频道成功
    },
    onLeaveChannel: function () {
        // 离开频道
    },
    onError: function (error) {
        // 发生异常
    }
});
```


* #### 加入频道

```javascript
client.joinChannel(channelId, uid, option);
```

| 参数 | 是否必须 | 描述 |
| ---- | :---- | :---- |
| channelId | 是 | 频道id，长度不超过40的字符串，支持的字符集范围: a-z,A-Z,0-9,_,- |
| uid | 是 | 用户id，为空时sdk会生成一个uid。长度不超过40的字符串，支持的字符集范围: a-z,A-Z,0-9,_,- |
| option | 否 | json对象，选项，可以配置最大时长，是否录音和透传数据 |

示例代码:
```javscript
client.joinChannel('123', 'tomweb', {
    isRecord: false, // 是否录音，默认为false
    maxDuration: 0, // 最大通话时长，0为不限制，默认为0
    extraData: '' // 透传数据，默认为''
});
```


* #### 离开频道

```javascript
client.leaveChannel();
```

<br>

#### 更多内容请参考：[https://www.feiyucloud.com](https://www.feiyucloud.com)

<br/>
