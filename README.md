<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"> <!-- 设置文档字符编码为UTF-8 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- 响应式视口设置，适配不同设备 -->
    <title>随机排序—lan</title> <!-- 网页标题 -->
    <style>
        body {
 margin: 0;
            font-family: Arial, sans-serif;
            /* 为底部留出3cm的空白 */
            padding-bottom: 3cm;
            display: flex;
            flex-direction: column;
            min-height: 100vh; /* 确保body占满视口高度 */


            font-family: Arial, sans-serif; /* 设置字体 */
        }
/* 顶部菜单栏样式 */
.navbar {
            position: sticky;
            top: 0;
            background-color: #333;
            color: white;
            padding: 10px 0;
            text-align: center;
            z-index: 10; /* 确保菜单栏在其他内容之上 */
        }

        .container {
            text-align: center; /* 文本居中 */
        }
        textarea {
            width: 900px; /* 文本框宽度 */
            height: 200px; /* 文本框高度 */
            padding: 10px; /* 内边距 */
            margin-bottom: 10px; /* 下外边距 */
        }
        button {
            padding: 10px 20px; /* 内边距 */
        }
        ul {
            list-style-type: none; /* 移除列表项前面的标记 */
            padding: 0; /* 移除默认内边距 */
        }
        li {
            margin: 5px 0; /* 上下外边距 */
        }
 .top-spacing {
            height: 96px; /* 定义高度为96px */
            margin-top: 96px; /* 顶部外边距为96px，这将创建视觉上的空白区域 */
            /* 如果你想确保这个空白区域是一个透明的块，而不影响布局，可以使用以下样式 */
            width: 100%; /* 宽度为100%，根据需要调整 */
            display: block; /* 默认为块级元素，但显式声明有助于理解 */
            background-color: transparent; /* 背景颜色设置为透明 */
            /* 如果不需要高度，仅使用margin-top即可 */
        }
a {
    text-decoration: none;
}
 
/* 修改超链接的颜色 */
a {
    color: white; /* 或者任何你想要的颜色 */
}
a {
            text-decoration: none;
            /* 修改超链接的颜色 */
            color: white;
        }
    </style>
</head>
<body>
 <!-- 顶部菜单栏 -->
    <div class="navbar">
        全代码已开源github   →   <a href="https://github.com/lanlan1971">点此访问</a>
    </div>
<!-- 使用类选择器添加顶部空白区域 -->
<div class="top-spacing"></div>
    <div class="container"> <!-- 容器div，用于居中文本框和按钮 -->
        <textarea id="inputText" placeholder="请输入内容，每行用换行符分隔..."></textarea> <!-- 文本框，用于输入内容 -->
        <button onclick="parseAndRandomize()">确认</button> <!-- 按钮，点击时调用parseAndRandomize函数 -->
        <ul id="outputList"></ul> <!-- 无序列表，用于显示处理后的列表项 -->
<p class="center-text">部分引用：百度AI</p>
<p class="center-text">本网页提供的信息和功能均基于现有技术和资源，仅作为学习交流，请在24h内删除</p>
<p class="center-text">用户应确保在使用本软件时遵守相关法律法规，并尊重他人的合法权益</p>
<p class="center-text">对于因使用本网页而造成的任何损失或损害，应自行承担相关风险，网页开发者不承担任何责任</p>
    </div>

    <script>
        function parseAndRandomize() {
            // 获取文本框的值
            var inputText = document.getElementById('inputText').value;

            // 使用换行符将文本内容分割成数组
            var lines = inputText.split('\n');

            // 创建一个空数组，用于存储列表项元素
            var listItems = [];

            // 遍历分割后的数组
            for (var i = 0; i < lines.length; i++) {
                // 去除每行首尾的空格
                var trimmedLine = lines[i].trim();

                // 如果行不为空，则创建一个列表项元素并添加到listItems数组中
                if (trimmedLine !== '') {
                    var listItem = document.createElement('li'); // 创建列表项元素
                    listItem.textContent = trimmedLine; // 设置列表项元素的文本内容
                    listItems.push(listItem); // 将列表项元素添加到数组中
                }
            }

            // 随机排序列表项元素
            listItems.sort(function() {
                return 0.5 - Math.random();
            });

            // 清空之前的列表项
            var outputList = document.getElementById('outputList');
            outputList.innerHTML = '';

            // 将随机排序后的列表项元素添加到无序列表中
            for (var j = 0; j < listItems.length; j++) {
                outputList.appendChild(listItems[j]);
            }
        }
    </script>
</body>
</html>
