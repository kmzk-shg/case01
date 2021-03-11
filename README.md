# 修正をmaster(main)にマージするまでの流れを知りたい。


>ブラウザから操作
## 1.リポジトリをフォークする
https://github.com/git-study-session-demo/case01

![スクリーンショット 2021-03-09 13 29 23](https://user-images.githubusercontent.com/869103/110418883-96bb9100-80db-11eb-8b64-5597f8ca3d56.png)

>コマンドから操作
## 2.フォークしたリポジトリをローカルにクローンして、その中に入る
<img width="1438" alt="スクリーンショット 2021-03-09 18 12 33" src="https://user-images.githubusercontent.com/71377103/110447498-a51da300-8103-11eb-87a8-962850d21c04.png">

```bash
git clone <your repository url> case01
cd case01
```
### 3.開発ブランチを作成する

```
git switch -c feature/case0101
```
## 4.サンプルファイルを追加して、そのファイルをコミットしてリモートの開発ブランチにプッシュする

```
touch sample.txt
echo "hello, world" > sample.txt
git add sample.txt
git commit -m 'add sample.txt'
git push origin feature/case0101
```
>ブラウザから操作
## 5.リポジトリのトップ画面からPRを作成する
<img width="1433" alt="スクリーンショット 2021-03-11 18 12 01" src="https://user-images.githubusercontent.com/71377103/110765323-6a4c7400-8297-11eb-8013-5732126ca78c.png">

**※※マージ先が自分のリポジトリになっているか確認してください。※※**
![スクリーンショット 2021-03-11 18 09 57](https://user-images.githubusercontent.com/71377103/110765456-89e39c80-8297-11eb-8d8d-8e70bc3d86dd.png)


**PRを作成する**
<img width="1033" alt="スクリーンショット 2021-03-11 18 10 32" src="https://user-images.githubusercontent.com/71377103/110766182-3f165480-8298-11eb-8a8d-c5b8f28a5ee0.png">


## 6.PRを確認してマージする
<img width="1433" alt="スクリーンショット 2021-03-11 18 13 44" src="https://user-images.githubusercontent.com/71377103/110765848-ee9ef700-8297-11eb-917f-ad09c3961f3d.png">


## 7.PRをマージ終わるとPR用ブランチを削除
<img width="1433" alt="スクリーンショット 2021-03-11 18 14 03" src="https://user-images.githubusercontent.com/71377103/110765930-01b1c700-8298-11eb-9b88-bae7a3d6deae.png">


>先ほど追加したファイルはmainブランチに反映していることを確認>

>コマンドから操作
## 8.ローカルmainブランチに戻って更新する

```
git switch main
git pull origin main
ls
```

>ローカルにも先ほど追加したファイルはmainブランチに反映していることを確認>
## 9.ローカルの開発ブランチを削除

```
git branch -d feature/case0101
```
