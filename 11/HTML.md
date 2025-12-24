HTMlは基礎は学んでいると思っていたが、開発や勉強している間にこのコードどういう意味か分からなかったりするのでこの機会に復習。そしてFlexboxが抜けておりなんなのかよくわからなかったので改めて学びなおしていく。

使っているテキストエディタは

### Visual Studio Code - The open source AI code editor

https://code.visualstudio.com/

バージョンは1.107で問題なく動作した。

復習といっても最初から学ぶのではなく、HTML CSSを使って何か作り
その時にわからないコードがあったりしたら調べて…というやり方でやあて行く。

主にFlexboxとフォームパーツにフォーカスをあてているので簡単な入会フォームを作って
学びなおした。

以下コード↓

<!DOCTYPE html>

<html lang="ja">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>入会フォーム</title>

  

    <link rel="stylesheet" href="css/style.css">

</head>

<body>

    <div class="container">

        <h1>入会フォーム</h1>

        <form action="" method="post">

            <div class="form-group">

                <label for="myname">お名前<span class="required">必須</span></label>

                <input type="text" id="myname" name="myname" placeholder="例：山本" required>

  

            </div>

            <div class="form-group">

                <label for="email">メールアドレス<span class="required">必須</span></label>

                <input type="email" id="email" name="email" placeholder="例：exampel@example.com">

            </div>

  

            <div class="form-group">

                <label>性別</label>

                <div class="radio-group">

                    <label>

                        <input type="radio" name="gender" value="male">

                        <span>男性</span>

                    </label>

  

                    <label>

                        <input type="radio" name="gender" value="female">

                        <span>女性</span>

                    </label>

  

                    <label>

                        <input type="radio" name="gender" value="" checked>

                        <span>その他・回答しない</span>

                    </label>

  

                </div>

            </div>

  

            <div class="form-group">

                <label>興味がある分野</label>

                <div class="checkbox-group">

                    <label>

                        <input type="checkbox" name="interest[]" value="スポーツ">

                        <span>スポーツ</span>

                    </label>

  

                    <label>

                        <input type="checkbox" name="interest[]" value="音楽">

                        <span>音楽</span>

                    </label>

  

                    <label>

                        <input type="checkbox" name="interest[]" value="アート">

                        <span>アート</span>

                    </label>

  

                    <label>

                        <input type="checkbox" name="interest[]" value="テクノロジー">

                        <span>テクノロジー</span>

                    </label>

                </div>
                
            </div>

            <div class="form-group">

                <label for="membership">会員種目<span class="required">必須</span></label>

                 <select id="membership" name="membership" required>

                    <option value="">選択してください</option>

                     <option value="regular">一般会員</option>

                     <option value="student">学生会員</option>

                     <option value="senior">シニア会員</option>

                 </select>

            </div>

  

            <div class="form-group">

                <label for="message">お問い合わせ内容<span class="required">必須</span></label>

                <textarea id="membership" name="message" rows="4" required></textarea>

            </div>

  

            <button type="submit">送信</button>

        </form>

    </div>

</body>

</html>

以下CSS↓

@import url('normalize.css');

  

:root {

    background-color: aliceblue;

}

  

body {

    display: flex;

    justify-content: center;

    padding: 20px;

}

  

.container {

    width: 100%;

    max-width: 600px;

    background-color: rgb(147, 212, 104);

    padding: 20px;

    border-radius: 8px;

}

  

h1 {

    text-align: center;

    margin-bottom: 2rem;

    color: rgb(75, 72, 72);

    font-size: 1.8rem;

}

  

.form-group {

    margin-bottom: 1.5rem;

}

  

input[type="text"],

input[type="email"],

select,

textarea {

    border: 1px solid#ddd;

    border-radius: 4px;

    font-size: 16px;

    width: 100%;

}

  

label {

    display: block;

    font-weight: bold;

    margin-bottom: 0.5rem;

}

  

button{

    background-color: rgb(171, 108, 31);

    color: #ddd;

    border: none;

    padding: 10px 20px;

    border-radius: 4px;

    cursor: pointer;

    font-size: 1rem;

    width: 100%;

    transition: background-color .3s;

}

  

button:hover {

    background-color: brown;

}

  

.required {

    background-color: rgb(193, 26, 151);

    padding: 2px 4px;

    font-size: .8em;

    border-radius: 2px;

    margin-left: 4px;

    color: #fff;

}

  

.radio-group,

.checkbox-group {

    display: flex;

    gap: 1.5rem;

    margin-top: .5rem;

}

  

.radio-group label,

.checkbox-group label {

    display: flex;

    align-items: center;

    font-weight: normal;

    margin: 0;

    gap: .5rem;

}

  

@media (max-width: 680px) {

    .radio-group,

    .checkbox-group{

        flex-direction: column;

        gap: .5rem;

    }

}

Flexbox

 ・ボタンを 横並び にする
 ・要素を 中央揃 にする
 ・画面サイズが変わっても 崩れにくい配置
 ・等間隔に並べる

body {

    display: flex;

    justify-content: center;

    padding: 20px;

}

これで横に並ぶ。
Flexboxは単に横並びにするということではなくて、柔軟性を持たせるという意味があるらしい。

.center {
  display: flex;
  justify-content: center;
  align-items: center;
}

これだけで横ならべになる。
フレーズ管理WEBアプリでは必須な技術

フォームパーツ

・コピーしたい文章を入力
・入力
・共有用の入力（できたら）

に必要技術

textarea buttonは特に必要

textarea 

文章を入力するための入力欄

<textarea id="textInput" rows="4"></textarea>
これでおけ
rows  高さ
id jsから習得するために必要

button

クリックして処理を時刻する部分

<button id="copyBtn">コピー</button>

これで機能する