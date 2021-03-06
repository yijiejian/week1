Hi 蔡哥和你介紹 Git 怎麼使用
Git 就是一個版本控制的工具，假設你想了一個段子覺得不錯簡稱 A ，後來你想在 A 版本新增一個橋段簡稱 A2，但是途中瓜及覺得你這 A 版本的內容不太OK想修改，這時就會出現問題，瓜及看到的是 A 版本，但你已經想好一個 A2 的新橋段要添加，這時候就需要版本控制，也就是說你現在需要複製一個分支 A2，同時讓瓜及修改原始版 A 的要求，以及菜哥分支 A2 也新增好橋段，最終把 A 和 A2 版結合再一起成最終版。

那這個流程要怎麼用 Git 指令執行呢?
1.首先我們要先建立一個 Git 環境做版本控制，讓菜哥的資料夾段子可以使用 Git 指令：git init
2,當菜哥想好了一個橋段簡稱 A ，想對他做版本控制，那我們要使用 Git 加入版本控制指令：git add A
3.這時候我們可以看一下目前的版本狀態，可以使用 Git 指令確認狀態：git status，status，可以看到A橋段已經被加入版本控制內。
4.當菜哥覺得這個橋段 A 已經完成不做修改時，我們可以新建一個版本，這時候我們可以>使用 Git 指令新建版本：git commit -m "菜哥橋段A版"，-m的意思是我們要這個階段的版
本命名，我們把它命名為「菜哥橋段A版」。
5,瓜及看過菜哥橋段後覺得 A 橋段可以再修改時，修改完成的 A 橋段我們需要再把他加入版本控制並為這個修改版本命名，一樣使用 git add A ,再來 got commit -m "菜哥橋段A修改版"
6.我們這時候可以看看目前版本有哪幾個，可以用 Git 指令去查看：git log
7.若菜哥覺得瓜及改得不太好想要用原始的 A 橋段，這時候我們可以使用 Git 指令回到過去的版本：git checkout 原本的版本號(利用 git log查詢版本號)
8.假設菜哥覺得 A 橋段想再加一個更好笑的段子簡稱 A2，這時為了避免版本混亂毛多的瓜及又要修改原始的 A 橋段，可以使用 Git 指令新增出一個分支複製 A 的橋段去進行修正：git branch A2
9.若菜哥要到 A2 去寫橋段時，這時候我們要用 Git 指令切換到 A2 的分支去：git checkout A2
10.菜哥已經把 A 和 A2 橋段寫好要合併時，這時我們可以下 Git 指令：git merge A2(這時A2可以刪掉，因為已經合併可不再使用)
11.若菜哥 A 橋段和 A2 橋段同時修改再做合併時會出現衝突 conflict，那就需要解決。
12.菜哥把最終版 commit 好為菜哥最終版，這時我們要上傳至 Github 上，第一步我要先從 GitHub上 repo一個專案命名為 A ，再來需要在本地端下 Git 指令：git push origin A(master)，這時候就會上傳到 GitHub 上
13.如果菜哥在 GitHub 上更新橋段，想要把新版本 Copy 一份到本地端，這時可以下 Git 指令：git pull origin A(master)
