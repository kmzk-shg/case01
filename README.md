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
![スクリーンショット 2021-03-09 13 36 52](https://user-images.githubusercontent.com/869103/110419853-71c81d80-80dd-11eb-9b07-d6fd7b2ccb3c.png)
![スクリーンショット 2021-03-09 13 37 59](https://user-images.githubusercontent.com/869103/110419872-7987c200-80dd-11eb-8e0d-a5b15c425360.png)

## 6.PRを確認してマージする

**※※マージ先が自分のリポジトリになっているか確認してください。※※**

![スクリーンショット 2021-03-09 13 39 18](https://user-images.githubusercontent.com/869103/110419916-91f7dc80-80dd-11eb-89e7-94aa8cbfb9b6.png)
## 7.PRをマージ終わるとPR用ブランチを削除
![スクリーンショット 2021-03-09 13 41 25](https://user-images.githubusercontent.com/869103/110419977-afc54180-80dd-11eb-86b0-5ada1d6d4484.png)

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
