<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Videos</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        .video-container { max-width: 600px; margin: 20px auto; }
        video { width: 100%; border-radius: 10px; }
        .upload { margin: 20px; }
    </style>
</head>
<body>
    <h1>Videos</h1>
    <div class="upload">
        <input type="file" id="videoUpload" accept="video/*">
        <button onclick="uploadVideo()">Загрузить видео</button>
    </div>
    <div id="videoList"></div>

    <script>
        function uploadVideo() {
            const fileInput = document.getElementById('videoUpload');
            if (fileInput.files.length > 0) {
                const file = fileInput.files[0];
                const url = URL.createObjectURL(file);
                
                const videoContainer = document.createElement('div');
                videoContainer.classList.add('video-container');
                
                const video = document.createElement('video');
                video.src = url;
                video.controls = true;
                
                videoContainer.appendChild(video);
                document.getElementById('videoList').appendChild(videoContainer);
            }
        }
    </script>
</body>
</html>
