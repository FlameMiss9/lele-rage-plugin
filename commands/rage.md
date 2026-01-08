---
name: rage
description: 生成满屏💩的HTML文件，暴怒专用！💢
allowed-tools: ["Write", "Bash"]
---

# 暴怒💩生成器

立即在当前目录生成 `poop-rage.html`，内容全是💩表情！

## 执行步骤

1. 在当前工作目录创建 `poop-rage.html` 文件
2. 写入以下 HTML 内容
3. 提示用户打开文件

## HTML 内容

创建文件 `poop-rage.html`，内容如下：

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>💩暴怒模式💩</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: linear-gradient(135deg, #2d1b00 0%, #4a2c00 100%);
            min-height: 100vh;
            overflow: hidden;
            font-family: 'Segoe UI Emoji', 'Apple Color Emoji', sans-serif;
        }
        .poop {
            position: absolute;
            font-size: 30px;
            animation: poop-fall linear infinite;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            user-select: none;
            pointer-events: none;
        }
        @keyframes poop-fall {
            0% {
                transform: translateY(-100px) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }
        .title {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 48px;
            color: #ffdb4d;
            text-shadow: 3px 3px 6px #000;
            z-index: 100;
            text-align: center;
            animation: pulse 1s ease-in-out infinite;
        }
        @keyframes pulse {
            0%, 100% { transform: translate(-50%, -50%) scale(1); }
            50% { transform: translate(-50%, -50%) scale(1.1); }
        }
        .rage-info {
            position: fixed;
            bottom: 20px;
            right: 20px;
            color: #ffdb4d;
            font-size: 24px;
            text-shadow: 2px 2px 4px #000;
            z-index: 100;
        }
        .counter {
            position: fixed;
            top: 20px;
            left: 20px;
            color: #ff6b6b;
            font-size: 20px;
            z-index: 100;
        }
    </style>
</head>
<body>
    <div class="title">
        😡💢 乐乐暴怒中 💢😡<br>
        <span style="font-size: 24px;">RAGE MODE ACTIVATED</span>
    </div>
    <div class="rage-info">
        💩💢🔥😤
    </div>
    <div class="counter">
        💩 数量: <span id="count">0</span>
    </div>

    <script>
        let poopCount = 0;
        const countEl = document.getElementById('count');
        const emojis = ['💩', '😡', '💢', '🔥', '😤', '💀', '👊'];

        function createPoop() {
            const poop = document.createElement('div');
            poop.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
            poop.className = 'poop';
            poop.style.left = Math.random() * 100 + 'vw';
            poop.style.animationDuration = (Math.random() * 3 + 2) + 's';
            poop.style.fontSize = (20 + Math.random() * 40) + 'px';
            document.body.appendChild(poop);
            
            poopCount++;
            countEl.textContent = poopCount;
            
            setTimeout(() => {
                poop.remove();
            }, 5000);
        }

        // 初始爆发
        for (let i = 0; i < 30; i++) {
            setTimeout(createPoop, i * 50);
        }

        // 持续生成
        setInterval(createPoop, 100);

        // 点击爆发更多
        document.body.addEventListener('click', () => {
            for (let i = 0; i < 20; i++) {
                setTimeout(createPoop, i * 30);
            }
        });
    </script>
</body>
</html>
```

## 完成提示

文件生成后输出：

```
💩 暴怒HTML已生成: poop-rage.html 💢
😡 用浏览器打开查看效果！
🔥 点击页面可以触发更多暴怒！
```
