<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Discord Webhook Sender</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #36393f;
            color: #dcddde;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            background-color: #2f3136;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
            width: 100%;
            max-width: 400px;
        }
        h2 {
            margin-top: 0;
            color: #ffffff;
            text-align: center;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            font-size: 14px;
        }
        textarea {
            width: 100%;
            height: 100px;
            background-color: #40444b;
            color: #dcddde;
            border: 1px solid #202225;
            border-radius: 5px;
            padding: 10px;
            box-sizing: border-box;
            resize: vertical;
            font-family: inherit;
        }
        textarea:focus {
            outline: none;
            border-color: #5865F2;
        }
        input[type="file"] {
            background-color: #40444b;
            padding: 8px;
            border-radius: 5px;
            width: 100%;
            box-sizing: border-box;
            cursor: pointer;
        }
        .checkbox-label {
            display: flex;
            align-items: center;
            cursor: pointer;
            font-weight: normal;
        }
        .checkbox-label input {
            margin-right: 10px;
            cursor: pointer;
        }
        button {
            width: 100%;
            padding: 12px;
            background-color: #5865F2;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        button:hover {
            background-color: #4752C4;
        }
        #status {
            margin-top: 15px;
            text-align: center;
            font-size: 14px;
            min-height: 20px;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>웹훅 전송기</h2>
    
    <div class="form-group">
        <label for="message">메시지 내용</label>
        <textarea id="message" placeholder="디스코드로 보낼 메시지를 입력하세요..."></textarea>
    </div>

    <div class="form-group">
        <label for="imageUpload">이미지 업로드 (선택)</label>
        <input type="file" id="imageUpload" accept="image/*">
    </div>

    <div class="form-group">
        <label class="checkbox-label">
            <input type="checkbox" id="useEmbed"> 임베드(Embed) 형태로 보내기
        </label>
    </div>

    <button id="sendBtn">보내기</button>
    <div id="status"></div>
</div>

<script>
    // 입력하신 웹훅 URL
    const WEBHOOK_URL = "https://discord.com/api/webhooks/1500116629462454333/8AZKyhzzH77JY1_4TfoEimY7P-mwMXnystMW5MPMeD7AZLny9HMx_ea0ofN5oajLSuJT";

    document.getElementById('sendBtn').addEventListener('click', async () => {
        const messageInput = document.getElementById('message');
        const imageInput = document.getElementById('imageUpload');
        const useEmbed = document.getElementById('useEmbed').checked;
        const statusEl = document.getElementById('status');

        const messageText = messageInput.value.trim();
        const imageFile = imageInput.files[0];

        // 메시지나 이미지 둘 중 하나는 있어야 전송 가능
        if (!messageText && !imageFile) {
            statusEl.textContent = "메시지나 이미지를 입력해주세요.";
            statusEl.style.color = "#ed4245"; // 디스코드 레드
            return;
        }

        statusEl.textContent = "전송 중...";
        statusEl.style.color = "#fee75c"; // 디스코드 옐로우

        try {
            // 디스코드 API로 보낼 JSON 페이로드 구조 만들기
            let payload = {};

            if (useEmbed) {
                payload.embeds = [{
                    description: messageText || null,
                    color: 5814783 // 임베드 테두리 색상 (파란색)
                }];
                // 이미지가 첨부되었다면 임베드 안에 이미지 URL을 파일명으로 참조 연결
                if (imageFile) {
                    payload.embeds[0].image = { url: `attachment://${imageFile.name}` };
                }
            } else {
                payload.content = messageText || null;
            }

            let fetchOptions = {
                method: 'POST'
            };

            // 이미지가 있을 경우 FormData를 사용하여 멀티파트 전송
            if (imageFile) {
                const formData = new FormData();
                formData.append('file', imageFile, imageFile.name);
                formData.append('payload_json', JSON.stringify(payload));
                fetchOptions.body = formData;
            } else {
                // 이미지가 없을 경우 일반 JSON 전송
                fetchOptions.headers = { 'Content-Type': 'application/json' };
                fetchOptions.body = JSON.stringify(payload);
            }

            // 웹훅으로 요청 보내기
            const response = await fetch(WEBHOOK_URL, fetchOptions);

            if (response.ok) {
                statusEl.textContent = "✅ 성공적으로 전송되었습니다!";
                statusEl.style.color = "#57F287"; // 디스코드 그린
                
                // 전송 성공 시 입력창 초기화
                messageInput.value = '';
                imageInput.value = '';
            } else {
                const errText = await response.text();
                statusEl.textContent = `❌ 전송 실패 (${response.status})`;
                statusEl.style.color = "#ed4245";
                console.error('Webhook Error:', errText);
            }
        } catch (error) {
            statusEl.textContent = `❌ 에러 발생: ${error.message}`;
            statusEl.style.color = "#ed4245";
            console.error('Fetch Error:', error);
        }
    });
</script>

</body>
</html>
