# mychat
学习项目-（使用MUI+H5+创建混合APP)

### 搭建首页框架

* muitab

	1. 使用示例

	```html
	<nav class="mui-bar mui-bar-tab">
		<a class="mui-tab-item mui-active" tabindex="0">
			<span class="mui-icon mui-icon-weixin"></span>
			<span class="mui-tab-label">轻聊</span>
		</a>
		<a class="mui-tab-item" tabindex="1">
			<span class="mui-icon mui-icon-contact"></span>
			<span class="mui-tab-label">通讯录</span>
		</a>
		<a class="mui-tab-item" tabindex="2">
			<span class="mui-icon mui-icon-navigate"></span>
			<span class="mui-tab-label">发现</span>
		</a>
		<a class="mui-tab-item" tabindex="3">
			<span class="mui-icon mui-icon-person"></span>
			<span class="mui-tab-label">我</span>
		</a>
	</nav>
	```

* tab页面切换

	1. mui 批量绑定事件

	```javascript
	// 批量绑定tap事件
	mui(".mui-bar-tab").on("tap", "a", function() {
		var tabindex = this.getAttribute("tabindex");
		
		// 显示点击的tab选项所对应页面
		plus.webview.show(fragments[tabindex].pageId, "fade-in", 200);
		for (var i = 0; i < fragments.length; i++) {
			if (i != tabindex) {
				plus.webview.hide(fragments[i].pageId, "fade-out", 200);
			}
		}
	});
	```

