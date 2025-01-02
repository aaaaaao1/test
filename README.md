# test
<!DOCTYPE html>

<html lang="ja">

<head>

  <meta charset="UTF-8">

  <title>巳年のロッテリーおみくじ</title>

  <style>

    body {

      font-family: sans-serif;

      margin: 2rem;

    }

    h1 {

      color: #006400;

      margin-bottom: 1rem;

    }

    select, button {

      padding: 0.5rem;

      font-size: 1rem;

    }

    #result {

      margin-top: 1rem;

      padding: 1rem;

      border: 1px solid #ccc;

      border-radius: 4px;

      max-width: 400px;

    }

    #result h2 {

      color: #f08080;

      margin-bottom: 0.5rem;

    }

  </style>

</head>

<body>



  <h1>巳年のロッテリーおみくじ</h1>

  <p>1～6 の数字を選んで「おみくじ結果を確認」ボタンを押してください。</p>



  <select id="numberSelect">

    <option value="">選択してください</option>

    <option value="1">1</option>

    <option value="2">2</option>

    <option value="3">3</option>

    <option value="4">4</option>

    <option value="5">5</option>

    <option value="6">6</option>

  </select>

  <button id="checkButton">おみくじ結果を確認</button>



  <div id="result"></div>



  <script>

    // おみくじ結果のデータをオブジェクトでまとめて管理

    const fortunes = {

      1: {

        title: '大吉',

        body: '脱皮するように大きな飛躍が期待できる年！\n思いきったチャレンジで、目標をぐんと引き寄せましょう。'

      },

      2: {

        title: '中吉',

        body: '焦らずゆっくり、でも確実に前へ進む運気。\n周りのサポートをうまく取り入れて、安定感を大事にすると吉です。'

      },

      3: {

        title: '小吉',

        body: '視野を広げると、思わぬチャンスが巡ってきそう。\n新しいことへの好奇心を忘れずに過ごしましょう。'

      },

      4: {

        title: '末吉',

        body: '大きな変化は控えめでも、今は力を蓄えるタイミング。\n地道な努力があとで大きく花開きます。'

      },

      5: {

        title: '凶',

        body: '準備不足でトラブルに巻き込まれる恐れが。\n無理をせず、慎重に進めることで逆に運気アップにつながります。'

      },

      6: {

        title: '大凶',

        body: '波乱含みですが、ここでの学びは将来の宝。\n落ち着いて足元を固めると、やがて逆転のチャンスをつかめます。'

      }

    };



    // ボタンをクリックした時の処理を設定

    document.getElementById('checkButton').addEventListener('click', function() {

      const select = document.getElementById('numberSelect');

      const value = select.value;

      const resultDiv = document.getElementById('result');

      

      if (!value) {

        // 数字が未選択の場合

        resultDiv.innerHTML = '<p>数字を選択してください。</p>';

      } else {

        // 選択された数字に応じたおみくじ結果を表示

        const fortune = fortunes[value];

        // 改行コード \n を <br> に変換して表示

        const formattedBody = fortune.body.replace(/\n/g, '<br>');

        resultDiv.innerHTML = `

          <h2>${fortune.title}</h2>

          <p>${formattedBody}</p>

        `;

      }

    });

  </script>



</body>

</html>
