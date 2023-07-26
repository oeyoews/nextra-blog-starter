```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="UTF-8" />
    <title>ChatGPT UI</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
      tailwind.config = { corePlugins: { preflight: false } };
    </script>
  </head>
  <body class="bg-gray-200 p-20">
    <div class="w-3/4 mx-auto bg-white rounded overflow-hidden shadow-lg">
      <div class="bg-blue-500 text-white py-4 px-6 font-bold text-xl">
        ChatGPT
      </div>
      <div class="px-4 py-6">
        <div id="messageContainer" class="overflow-y-auto max-h-96"></div>
        <form onsubmit="sendMessage(event)">
          <div class="flex mt-4">
            <input
              type="text"
              id="userInput"
              class="flex-1 bg-gray-100 rounded-l py-2 px-4 focus:outline-none border-none"
              placeholder="请输入消息"
            />
            <button
              type="submit"
              class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-r border-none"
            >
              发送
            </button>
          </div>
        </form>
      </div>
    </div>

    <script>
      function sendMessage(event) {
        event.preventDefault();

        var userInput = document.getElementById("userInput");
        var messageContainer = document.getElementById("messageContainer");

        // 获取用户输入的消息内容
        var userMessage = userInput.value.trim();

        if (userMessage !== "") {
          // 创建并添加用户消息元素
          var userMessageElement = document.createElement("div");
          userMessageElement.className =
            "py-2 px-4 rounded my-2 bg-blue-500 text-white";
          userMessageElement.textContent = userMessage;
          messageContainer.appendChild(userMessageElement);

          // 发送用户消息给后端进行处理，并获取对应的回复消息
          var botReply = getBotReply(userMessage);

          // 创建并添加机器人回复消息元素
          var botMessageElement = document.createElement("div");
          botMessageElement.className =
            "py-2 px-4 rounded my-2 bg-gray-200 text-gray-700 inline-block";
          botMessageElement.textContent = botReply;
          messageContainer.appendChild(botMessageElement);

          // 滚动到消息容器的底部以显示最新的消息
          messageContainer.scrollTop = messageContainer.scrollHeight;

          // 清空用户输入框
          userInput.value = "";
        }
      }

      function getBotReply(userMessage) {
        const predefinedAnswers = {
          你好: "你好，请问有什么可以帮助您的？",
          你叫什么名字: "我是 ChatGPT，很高兴为您服务。",
          天气怎么样: "很抱歉，我无法提供实时天气信息。",
        };

        if (predefinedAnswers.hasOwnProperty(userMessage)) {
          return predefinedAnswers[userMessage];
        }

        return "🧊 不好意思,我还没有想好啦。";
      }
    </script>
  </body>
</html>
```