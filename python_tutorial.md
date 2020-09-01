---
tags: python
---
# Python教學 #
## venv 建立 ##
1. 使用Python venv 模組功能建立虛擬環境
    <pre><code>python3 -m venv tutorial_env</code></pre>
2. 啟用虛擬環境
    <pre><code>source ~/Developer/Python/tutorial_env/bin/activate</code></pre>
3. 退出虛擬環境
    <pre><code>deactivate</code></pre>
<br>

******
## pip 指令 ##
1. 查詢套件
    <pre><code>pip search astronomy</code></pre>
    ```python=
    with open("number.txt") as file_object: # 開啟number.txt檔並將其存到file_object中
    content=file_object.read() # 讀取file_object的所有內容
    print(content.rstrip()) # 將印出的檔案刪除read()返回的一行空白
    ```
2. 安裝套件
    <pre><code>pip install novas</code></pre>
    <pre><code>pip install requests==2.6.0</code></pre>
3. 升級套件
    <pre><code>pip install --upgrade requests</code></pre>
4. 顯示套件資訊
    <pre><code>pip show requests</code></pre>
5. 套件列表
    <pre><code>pip list</code></pre>
6. 套件列表 輸出 requirments.txt
    <pre><code>pip freeze > requirements.txt</code></pre>
7. 由 requirments.txt 資料安裝套件
    <pre><code>pip install -r requirements.txt</code></pre>
<br>
