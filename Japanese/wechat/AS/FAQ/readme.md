#WeChatのよくある質問まとめ

>author：charley

####1、なぜミニゲームのローカルパッケージに入れたのですか？いくつかのリソースは正常にロードできません。

ローカルパッケージにファイルの拡張子に白いリストが設定されていますので、リスト内にない拡張子ファイルはアップロードできません。自然に使えなくなります。しかし、URLを使って動的にロードして、ローカルパッケージに入れずにアップロードすればいいです。


已知的文件类型白名单为：png、jpg、jpeg、gif、svg、js、json、cer、obj、dae、fbx、mtl、stl、3ds、mp3、pvr、wav、plist、ttf、fnt、gz、ccz、m4a、mp4、bmp、atlas、swf、ani、part、proto、bin、sk、mipmaps、txt、zip、tt、map、ogg、silk、dbbin、dbmv、etc、lmat、lm、ls、lh、lani、lav、lsani、ltc。



####2、なぜexactfit適合モードを設定しましたか？フルスクリーンでの引張が適切にできないですか？

WeChatはエンジンがcanvasのサイズをコントロールすることを許さない。ミニゲームのcanvasサイズは自動的に引き伸ばします。exactfitモードのstage幅の高さはずっと設計の幅の高さに等しくて、canvasが制御できない時、exactfitの適応は実は失効しました。ここではfixedatot、またはfullなどの設計幅の高さを考慮する必要はなく、自動的にstageの幅の高い適応モードを変えて、他の適応方案を組み合わせて試してみます。

例えば、fixedatot、またはfull適合モードを使用した後、背景図のtop、bottom、left、right属性を0に設定すると、フルスクリーンが敷かれます。



####3、H 5での効果は正常に表示されています。ミニゲームがリリースされた後、エラーメッセージがJSONに関連しています。

小さいゲームの中でローカルの資源を読んでコードを検査しますので、プロジェクトの中で圧倒的に多くの非ピクチャのファイルのコードはASCIIです。だからエンジンはローカルインターフェースを呼び出してファイルを読みます。デフォルトの転送は小さいゲームのコードフォーマットはASCIIコードです。ローカルの初期パッケージのファイル（例えば、jsonファイル）のコードフォーマットはASCIIではないと、エラーが発生します。ですから、開発者はファイルのコードを確認してから通過します。`MiniAdpter['getUrlEncode']`このファイルの本当のコードは何かを教えてください。これで正しいコードでチェックすれば間違いありません。


```js

//告诉小游戏你的文件编码是什么
MiniAdpter['getUrlEncode'] = getUrlAndEncode;//假如getUrlAndEncode是开发者识别文件编码的方法
```


開発者がファイルコードを識別する方法の例（AS 3版）：


```javascript

//该方法示例仅做参考，视项目情况自行修改或拓展
public static var getUrlAndEncode:Function = function(url:String,type:String):String
{
	if (url.indexOf(".fnt") != -1 || url.indexOf("xxx.json") != -1) 
    {
		return "utf8";
	} else if (type == "arraybuffer") 
    {
		return "";
	}
	return "ascii";
}
```




また、ネットワークから動的に読み込み、エンコードのチェック制限はありません。したがって、jsonをインターネットに置いて動的に読み込みを行うこともできます。



####4、声がloaderでプリロードできません。

オーディオの面では、HTML 5の元のブラウザとは違って、ミニゲームの下の環境は、音声インスタンスを作成するインターフェースをサポートしていません。したがって、ネットワークのオーディオファイルを直接にロードしてから使用することはできません。

SoundMangerオーディオ管理クラスで直接オーディオファイルを再生できます。

あるいは、プリローディングの必要がある場合は、キャッシュファイルを通じてダウンロードする方法で、まずファイルをローカルキャッシュにダウンロードし、キャッシュに存在することを確認してから、直接にローカルキャッシュのオーディオファイルを再生しても、プリローディングの効果があります。



####5、Mater物理エンジンはミニゲームでエラーを報告し、縦画面モードでマウスはイベント応答がない。

ミニゲームwindowの役割エリアの問題で、出現します。`Matter is not defined`の新聞が間違っています。または縦画面モードでは、マウスにイベントがありません。これらの問題はすでにエンジンバンクの1.7.20バージョンで、Matter.jsを修復しました。1.7.20以降のバージョンを使って、上記の問題を解決してください。ただし、LayaboxチームはMatter.jsを修正しました。今後はエンジンで提供されるMatter.jsだけを使って、第三者からMatter.jsを獲得してはいけません。

エンジンが更新されていない前にコミュニティに行くことができます。[下载](https://ask.layabox.com/question/15055)（下のリンク）ベスト解答の付属品mater.zipにあります。mater.jsを交替すればいいです。

[https://ask.layabox.com/question/15055](https://ask.layabox.com/question/15055)



###次の更新:

この文書では、開発者が微信小ゲームを開発する時に遭遇したよくある小さな問題をまとめて答えます。この文書に疑問があれば、公式サイトに質問してください。

コミュニティの開発者がフィードバックしたミニゲームによくある問題に対して、この文書は不定期的に更新されます。

コミュニティURL：https://ask.layabox.com/



##この文章は賞賛します

本論文があなたのために役立つと思ったら、スキャンコードの作者への賞賛を歓迎します。激励は私たちがより多くの優れた文書を書くための動力です。

![wechatPay](../../../wechatPay.jpg)