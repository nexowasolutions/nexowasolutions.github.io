<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JSON Files List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f5f5f5;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 30px;
        }
        .file-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            margin-bottom: 10px;
            background: #f8f9fa;
            border-radius: 5px;
            border-left: 4px solid #007bff;
        }
        .file-name {
            font-weight: bold;
            color: #333;
        }
        .copy-btn {
            background: #007bff;
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 14px;
        }
        .copy-btn:hover {
            background: #0056b3;
        }
        .copy-btn.copied {
            background: #28a745;
        }
        .no-files {
            text-align: center;
            color: #666;
            padding: 40px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>JSON Files</h1>
        <div id="fileList">
            <div class="no-files">Loading...</div>
        </div>
    </div>

    <script>
        async function scanDirectory() {
            try {
                const currentPath = window.location.pathname;
                const directoryPath = currentPath.substring(0, currentPath.lastIndexOf('/') + 1);
                
                const response = await fetch(directoryPath);
                if (response.ok) {
                    const html = await response.text();
                    parseDirectoryListing(html);
                } else {
                    showNoFiles();
                }
            } catch (error) {
                showNoFiles();
            }
        }

        function parseDirectoryListing(html) {
            const parser = new DOMParser();
            const doc = parser.parseFromString(html, 'text/html');
            const links = doc.querySelectorAll('a[href]');
            
            const jsonFiles = [];
            links.forEach(link => {
                const href = link.getAttribute('href');
                if (href && !href.startsWith('?') && !href.startsWith('#') && !href.includes('://')) {
                    const fileName = decodeURIComponent(href.replace(/\/$/, ''));
                    if (fileName && fileName !== '.' && fileName !== '..' && fileName.endsWith('.json')) {
                        jsonFiles.push(fileName);
                    }
                }
            });
            
            displayFiles(jsonFiles);
        }

        function displayFiles(files) {
            const fileList = document.getElementById('fileList');
            
            if (files.length === 0) {
                fileList.innerHTML = '<div class="no-files">No JSON files found</div>';
                return;
            }
            
            fileList.innerHTML = files.map(file => `
                <div class="file-item">
                    <div class="file-name">${file}</div>
                    <button class="copy-btn" onclick="copyFileName('${file}', this)">Copy</button>
                </div>
            `).join('');
        }

        function copyFileName(fileName, button) {
            navigator.clipboard.writeText(fileName).then(() => {
                button.textContent = 'Copied!';
                button.classList.add('copied');
                setTimeout(() => {
                    button.textContent = 'Copy';
                    button.classList.remove('copied');
                }, 2000);
            }).catch(() => {
                // Fallback for older browsers
                const textArea = document.createElement('textarea');
                textArea.value = fileName;
                document.body.appendChild(textArea);
                textArea.select();
                document.execCommand('copy');
                document.body.removeChild(textArea);
                
                button.textContent = 'Copied!';
                button.classList.add('copied');
                setTimeout(() => {
                    button.textContent = 'Copy';
                    button.classList.remove('copied');
                }, 2000);
            });
        }

        function showNoFiles() {
            document.getElementById('fileList').innerHTML = '<div class="no-files">Could not access directory</div>';
        }

        // Start scanning when page loads
        scanDirectory();
    </script>
</body>
</html> 