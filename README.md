# AOAI-first-step-for-Developer

## 概要

このハンズオンは [Microsoft Azure OpenAI サービス](https://learn.microsoft.com/ja-jp/azure/ai-services/openai/overview) が提供する生成 AI モデルを使用したアプリケーションを開発するために必要となる基本的な知識を身に着けるためのハンズオン コンテンツです。

AI そのものを開発するのではなく、**生成 AI モデルを利用したアプリケーションを開発するための**基本的なスキルを身に着けることが目的としています。

生成 AI モデルをエンジンに例えるのであれば、それらが用意している機能を活用して車やオートバイや、船を効率よく作るための技術を身に着けることを目的としています。

![ハンズオンのイメージ](images/handson_img.png)

よって、生成 AI モデルのファインチューニングやモデルの改良、新しいモデルの開発については触れません。

## 目的

生成 AI モデルを利用したアプリケーションを開発するためのファースト ステップとして必要な情報を提供し、実際に手を動かしながら学ぶことができるようにすることを目的としています。

Windows の \[**Start**\] ボタンのように、このハンズオンを実施することで受講者が次に学ぶべきことが何であるかを知ることができ、かつ、学習方法のガイドとなることを目指しています。

また、初学者でも学びやすいよう、AI 関連のサンプル コードによく使用される Python ではなく、Node.js を使用しますが、TypeScript ではなく、より利用者が多いであろう JavaScript を使用し、可能な限り簡潔かつ平易なコードで実装を行います。 

## ハンズオンの内容

このハンズオンでは実際に環境構築とコーディングを行いながら以下の内容を学びます。

- Azure OpenAI サービス リソースの作成
- Azure OpenAI Studio からの GPT モデルのデプロイと基本的な操作方法
- REST API を使用した GPT モデルの呼び出し
- Node.js 用 Azure OpenAI ライブラリを使用したボットアプリケーションの作成
- Function Calling を使用したボットアプリケーションへの任意の関数の統合
- RAG (Retrieval-Augmented Generation) の実装 
- 画像生成/認識機能の実装
- Structured Outputs を使用した構造化データの生成
- 演習で開発した機能のアプリケーション フレームワークへの移植
- Azure Bot によるサービスの公開
- Microsoft Teams へのデプロイ (オプション)

このハンズオンを終了すると、アプリケーションから Azure 上の GPT モデルのプロンプトを呼び出せるだけでなく、任意の内部、外部を含む関数を呼び出す仕組み、RAG を使用して独自の知識を追加する仕組みを理解することができます。

## 最終改訂履歴

### 2024 年　12 月 5 日

* Azure AI Studio の UI 画面ショットを最新のものに差し替えました。

* [演習 2.3 : 独自データの追加 - チャット プレイグランド画面から独自のデータを追加する](/Ex02-3.md#%E3%83%81%E3%83%A3%E3%83%83%E3%83%88-%E3%83%97%E3%83%AC%E3%82%A4%E3%82%B0%E3%83%A9%E3%83%B3%E3%83%89%E7%94%BB%E9%9D%A2%E3%81%8B%E3%82%89%E7%8B%AC%E8%87%AA%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B) の手順を `Upload files(Preview)` から `Azure Blob Storage(Preview)` の手順に変更しました。

* [演習 3. 5 : 画像認識機能の追加 - チャットボット アプリへの画像認識機能の統合](Ex03-5.md#%E3%82%BF%E3%82%B9%E3%82%AF-2---%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%83%9C%E3%83%83%E3%83%88-%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E7%94%BB%E5%83%8F%E8%AA%8D%E8%AD%98%E6%A9%9F%E8%83%BD%E3%81%AE%E7%B5%B1%E5%90%88) において、画像認識の際のリクエストへの detail プロパティの追加と説明コメントの追加を行いました。

    ```
    //トークンの消費量を抑えたい場合は detail プロパティを 'auto' から 'low' に変更
     _content.push({ type: 'image_url', image_url: { url: imageUrl, detail: 'auto' } });
    ```

* [ハンズオン終了後の目的別学習コンテンツ紹介](NextLearn.md) に **参考となるセッションビデオ** の項目を作成し、2024 年 11 月 27-28 日に開催された 「**AI-Ready Infra. Boot Camp ～ 拡張性のある AI 利用に向けた IT 基盤とは？ ～**」のセッションビデオへのリンクを追加しました。


これまでの更新内容は[改訂履歴](changelog.md)を参照してください。

<br>

## 対象者

このチュートリアルは以下の知識がある方を対象としています。

* **Microsoft Azure の基本的な知識**

    Azure のリソースを作成、操作するための基本的な(MCP [AZ-900](https://learn.microsoft.com/ja-jp/certifications/exams/az-900/) 程度の)知識が必要です。

* **Visual Studio Code を使用したコーディング経験**

    このチュートリアルでは、Visual Studio Code を使用して演習用ボットアプリケーションを作成します。Visual Studio Code でのコーディング経験が必要です。

## 要件

このチュートリアルを実施するには以下の環境が必要です。

- [**Microsoft Azure サブスクリプション**](https://azure.microsoft.com/ja-jp/free/) 

<!--
と Azure Open AI サービスの[利用資格](https://aka.ms/oaiapply)**

    >【重要】現在、Azure Open AI の利用は Microsoft と既存のパートナーシップ関係があるお客様、リスクの低いユース ケース、軽減策の取り入れに取り組んでいるお客様に制限されており、**利用には申請が必要**です。申請については、以下の申請フォームに記載されています。 利用を開始するにはこちらからお申し込みください。

    - [**Azure OpenAI Service へのアクセス申請**](https://aka.ms/oaiapply)
-->

- [**Visual Studio Code**](https://code.visualstudio.com/)

    Visual Studio Code から Azure のリソースを作成するための以下の拡張もインストールしてください。
    - [Azure Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)


- [**Node.js**](https://nodejs.org/ja/)

    - v22.11.0(LTS)バージョン (2024 年 11 月現在の最新の LTS) 


    > もし、V22.11.0 で動作しない場合は、v20.17.0 もしくは v20.18.0 の LTS バージョンでお試しください。なお、ローカル環境で Node.js のバージョンを切り替える必要がある場合には Windows では [**nvm-windows**](https://github.com/coreybutler/nvm-windows) 、Mac では [nvm](https://github.com/nvm-sh/nvm) を使用すると便利です。
    > 詳しくは以下のドキュメントを参照してください。

    - [**nvm-windows のインストール**](https://learn.microsoft.com/ja-jp/windows/dev-environment/javascript/nodejs-on-windows#install-nvm-windows-nodejs-and-npm)

    - [**nvm のインストール**](https://learn.microsoft.com/ja-jp/windows/dev-environment/javascript/nodejs-on-wsl#install-nvm-nodejs-and-npm)

## 演習

1. [**Azure Open AI リソースの作成**](Ex01-0.md)

    - [1.1 : Azure ポータルから Open AI リソースを作成する](Ex01-1.md)
    - [1.2 : Azure OpenAI Studio から言語モデル gpt-4o-mini のデプロイ](Ex01-2.md)
    - [1.3 : Azure OpenAI Studio から埋め込みモデル : text-embedding-ada-002 のデプロイ](Ex01-3.md)
    - [1.4 : Azure OpenAI Studio から画像生成モデル : dall-e-3 のデプロイ](Ex01-4.md)
	    
2. [**Azure OpenAI Studio からの AI モデルの利用**](Ex02-0.md)
    - [2.1 : システムメッセージとパラメーター設定](Ex02-1.md)
    - [2.2 :プロンプト エンジニアリング ](Ex02-2.md)
    - [2.3 : 独自データの追加](Ex02-3.md)
    - [オプション : Azure OpenAI Studio で作成したチャットボットを Azure App Service にデプロイ](Ex02-3.md#%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3--azure-openai-studio-%E3%81%A7%E4%BD%9C%E6%88%90%E3%81%97%E3%81%9F%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%83%9C%E3%83%83%E3%83%88%E3%82%92-azure-app-service-%E3%81%AB%E3%83%87%E3%83%97%E3%83%AD%E3%82%A4)

3. [**Azure Open AI サービスとアプリケーションの統合**](Ex03-0.md)
    - [3.1 : Azure Open AI サービスの API 利用](Ex03-1.md)
        - [タスク 1 : curl コマンドによる呼び出しの確認](Ex03-1.md#%E3%82%BF%E3%82%B9%E3%82%AF-1---curl-%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%81%AB%E3%82%88%E3%82%8B%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%AE%E7%A2%BA%E8%AA%8D)
        - [タスク 2 :  HTTP Client ツールによる呼び出しの確認](Ex03-1.md#%E3%82%BF%E3%82%B9%E3%82%AF-2-http-client-%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%AE%E7%A2%BA%E8%AA%8D)
    - [3.2 : ボット アプリケーションの作成](Ex03-2.md)
        - [タスク 1 : コンソールで動作するオウム返しアプリケーションの作成](Ex03-2.md#%E3%82%BF%E3%82%B9%E3%82%AF-1--%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%81%A7%E5%8B%95%E4%BD%9C%E3%81%99%E3%82%8B%E3%82%AA%E3%82%A6%E3%83%A0%E8%BF%94%E3%81%97%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90)
	    - [タスク 2 : Azure OpenAI ライブラリを利用した言語モデルへのメッセージの送信](Ex03-2.md#%E3%82%BF%E3%82%B9%E3%82%AF-2--azure-openai-%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%9F%E8%A8%80%E8%AA%9E%E3%83%A2%E3%83%87%E3%83%AB%E3%81%B8%E3%81%AE%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%81%AE%E9%80%81%E4%BF%A1)
        - [タスク 3 : コンソールで動作する基本的なチャットボット アプリの作成](Ex03-2.md#%E3%82%BF%E3%82%B9%E3%82%AF-3--%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%81%A7%E5%8B%95%E4%BD%9C%E3%81%99%E3%82%8B%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%83%9C%E3%83%83%E3%83%88-%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E4%BD%9C%E6%88%90)
    - [3.3 : Function Calling 機能を使用した任意の関数の実行](Ex03-3.md)
        - [タスク 1 : HTTP Client ツールによる呼び出しの確認(Function Calling)](Ex03-3.md#%E3%82%BF%E3%82%B9%E3%82%AF-1---http-client-%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%AE%E7%A2%BA%E8%AA%8Dfunction-calling)
	    - [タスク 2 : チャットボット アプリからの関数の呼び出し](Ex03-3.md#%E3%82%BF%E3%82%B9%E3%82%AF-2--%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%83%9C%E3%83%83%E3%83%88-%E3%82%A2%E3%83%97%E3%83%AA%E3%81%8B%E3%82%89%E3%81%AE%E9%96%A2%E6%95%B0%E3%81%AE%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97)
	    - [タスク 3 : 画像生成モデルの利用](Ex03-3.md#%E3%82%BF%E3%82%B9%E3%82%AF-3---%E7%94%BB%E5%83%8F%E7%94%9F%E6%88%90%E3%83%A2%E3%83%87%E3%83%AB%E3%81%AE%E5%88%A9%E7%94%A8)
            - [タスク 3-1 : HTTP Client ツールによる呼び出しの確認](Ex03-3.md#%E3%82%BF%E3%82%B9%E3%82%AF-3-1--http-client-%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%AE%E7%A2%BA%E8%AA%8D)
            - [タスク 3-2 : チャットボット アプリへの画像生成機能の統合](Ex03-3.md#%E3%82%BF%E3%82%B9%E3%82%AF-3-2--%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%83%9C%E3%83%83%E3%83%88-%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E7%94%BB%E5%83%8F%E7%94%9F%E6%88%90%E6%A9%9F%E8%83%BD%E3%81%AE%E7%B5%B1%E5%90%88)
    - [3.4 : RAG (Retrieval-Augmented Generation) の実装](Ex03-4.md)
        - [タスク 1: HTTP Client ツールによる問い合わせメッセージのベクトル化とベクトル検索](Ex03-4.md#%E3%82%BF%E3%82%B9%E3%82%AF-4-1--http-client-%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E5%95%8F%E3%81%84%E5%90%88%E3%82%8F%E3%81%9B%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%81%AE%E3%83%99%E3%82%AF%E3%83%88%E3%83%AB%E5%8C%96%E3%81%A8%E3%83%99%E3%82%AF%E3%83%88%E3%83%AB%E6%A4%9C%E7%B4%A2)
        - [タスク 2: チャットボット アプリに RAG の機能を追加](Ex03-4.md#%E3%82%BF%E3%82%B9%E3%82%AF-4-2--%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%83%9C%E3%83%83%E3%83%88-%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB-rag-%E3%81%AE%E6%A9%9F%E8%83%BD%E3%82%92%E8%BF%BD%E5%8A%A0)
    - [3.5 : 画像認識機能の追加](Ex03-5.md)
        - [タスク 1 : HTTP Client ツールによる呼び出しの確認(画像認識)](Ex03-5.md#%E3%82%BF%E3%82%B9%E3%82%AF-1---http-client-%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%AE%E7%A2%BA%E8%AA%8D%E7%94%BB%E5%83%8F%E8%AA%8D%E8%AD%98)
        - [タスク 2 : チャットボット アプリへの画像認識機能の統合](Ex03-5.md#%E3%82%BF%E3%82%B9%E3%82%AF-2---%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%83%9C%E3%83%83%E3%83%88-%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E7%94%BB%E5%83%8F%E8%AA%8D%E8%AD%98%E6%A9%9F%E8%83%BD%E3%81%AE%E7%B5%B1%E5%90%88)

    - [3. 6 : 言語モデルの応答に JSON を指定する](Ex03-6.md)
        - [タスク 1 : HTTP Client ツールによる呼び出しの確認(Structured Outputs)](Ex03-6.md#%E3%82%BF%E3%82%B9%E3%82%AF-1--http-client-%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%AE%E7%A2%BA%E8%AA%8Dstructured-outputs)
        - [タスク 2 : JavaScript コードからの呼び出しの確認](Ex03-6.md#%E3%82%BF%E3%82%B9%E3%82%AF-2--javascript-%E3%82%B3%E3%83%BC%E3%83%89%E3%81%8B%E3%82%89%E3%81%AE%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%AE%E7%A2%BA%E8%AA%8D)
    - [3. 7 : 演習用ボットをコンソール アシスタントとして利用する](Ex03-7.md)
    - [3.オプション : Web の情報を検索して回答する](Ex03-op-1.md)
        - [タスク 1 : HTTP Client ツールによる呼び出しの確認(Bing Web Search)](Ex03-op-1.md#%E3%82%BF%E3%82%B9%E3%82%AF-1---http-client-%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AB%E3%82%88%E3%82%8B%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%AE%E7%A2%BA%E8%AA%8Dbing-web-search)
        - [タスク 2 : Web 検索とコンテンツ取得を行う機能の実装](Ex03-op-1.md#%E3%82%BF%E3%82%B9%E3%82%AF-2--web-%E6%A4%9C%E7%B4%A2%E3%81%A8%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E5%8F%96%E5%BE%97%E3%82%92%E8%A1%8C%E3%81%86%E6%A9%9F%E8%83%BD%E3%81%AE%E5%AE%9F%E8%A3%85)
            - [タスク 2-1 : Web ページのコンテンツを取得する機能の実装](Ex03-op-1.md#%E3%82%BF%E3%82%B9%E3%82%AF-2-1--web-%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B%E6%A9%9F%E8%83%BD%E3%81%AE%E5%AE%9F%E8%A3%85)
            - [タスク 2-2 : Web ページのコンテンツから不要な HTML タグやスクリプト、スタイルシートを除去する機能の実装](Ex03-op-1.md#%E3%82%BF%E3%82%B9%E3%82%AF-2-2--web-%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%81%8B%E3%82%89%E4%B8%8D%E8%A6%81%E3%81%AA-html-%E3%82%BF%E3%82%B0%E3%82%84%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E3%82%B9%E3%82%BF%E3%82%A4%E3%83%AB%E3%82%B7%E3%83%BC%E3%83%88%E3%82%92%E9%99%A4%E5%8E%BB%E3%81%99%E3%82%8B%E6%A9%9F%E8%83%BD%E3%81%AE%E5%AE%9F%E8%A3%85)
            - [タスク 2-3 : Web 検索機能の実装と言語モデルへのメッセージの生成](Ex03-op-1.md#%E3%82%BF%E3%82%B9%E3%82%AF-2-3--web-%E6%A4%9C%E7%B4%A2%E6%A9%9F%E8%83%BD%E3%81%AE%E5%AE%9F%E8%A3%85%E3%81%A8%E8%A8%80%E8%AA%9E%E3%83%A2%E3%83%87%E3%83%AB%E3%81%B8%E3%81%AE%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%81%AE%E7%94%9F%E6%88%90)
        - [タスク 3: チャットボット アプリへの Web 検索機能の統合](Ex03-op-1.md#%E3%82%BF%E3%82%B9%E3%82%AF-3-%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%83%9C%E3%83%83%E3%83%88-%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE-web-%E6%A4%9C%E7%B4%A2%E6%A9%9F%E8%83%BD%E3%81%AE%E7%B5%B1%E5%90%88)

4. [**演習用ボットのアプリケーション フレームワークへの移植**](Ex04-0.md)
    - [4.1 : コンソールボットからの機能の移植](Ex04-1.md)
    - [4.2 : Azure リソースの作成とボットのデプロイ](Ex04-2.md)
        - [タスク 1 : Bot Service の作成](Ex04-2.md#%E3%82%BF%E3%82%B9%E3%82%AF-1--bot-service-%E3%81%AE%E4%BD%9C%E6%88%90)
        - [タスク 2 : ボット アプリケーションへの ID 設定と Azure App Service へのデプロイ](Ex04-2.md#%E3%82%BF%E3%82%B9%E3%82%AF-2--%E3%83%9C%E3%83%83%E3%83%88-%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%B8%E3%81%AE-id-%E8%A8%AD%E5%AE%9A%E3%81%A8-azure-app-service-%E3%81%B8%E3%81%AE%E3%83%87%E3%83%97%E3%83%AD%E3%82%A4)
        - [タスク 3. Azure Bot に Bot Framework ボットアプリケーションを登録する](Ex04-2.md#%E3%82%BF%E3%82%B9%E3%82%AF-3-azure-bot-%E3%81%AB-bot-framework-%E3%83%9C%E3%83%83%E3%83%88%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B)
    - [4.オプション 1 : Microsoft Teams へのインストール](Ex04-op-1.md)
    - [4.オプション 2 : Teams ボットへの画像認識機能の追加](Ex04-op-2.md)
*  [**ハンズオン終了後の目的別学習コンテンツ紹介**](NextLearn.md)
<br>


---
## LICENSE

このドキュメントに記載されている情報 (URL や他のインターネット Web サイト参照を含む) は、将来予告なしに変更することがあります。別途記載されていない場合、このソフトウェアおよび関連するドキュメントで使用している会社、組織、製品、ドメイン名、電子メール アドレス、ロゴ、人物、場所、出来事などの名称は架空のものです。実在する商品名、団体名、個人名などとは一切関係ありません。お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用をお願いいたします。著作権法による制限に関係なく、マイクロソフトの書面による許可なしに、このドキュメントの一部または全部を複製したり、検索システムに保存または登録したり、別の形式に変換したりすることは、手段、目的を問わず禁じられています。ここでいう手段とは、複写や記録など、電子的、または物理的なすべての手段を含みます。

マイクロソフトは、このドキュメントに記載されている内容に関し、特許、特許申請、商標、著作権、またはその他の無体財産権を有する場合があります。別途マイクロソフトのライセンス契約上に明示の規定のない限り、このドキュメントはこれらの特許、商標、著作権、またはその他の知的財産権に関する権利をお客様に許諾するものではありません。

製造元名、製品名、URL は、情報提供のみを目的としており、これらの製造元またはマイクロソフトのテクノロジを搭載した製品の使用について、マイクロソフトは、明示的、黙示的、または法令によるいかなる表明も保証もいたしません。製造元または製品に対する言及は、マイクロソフトが当該製造元または製品を推奨していることを示唆するものではありません。掲載されているリンクは、外部サイトへのものである場合があります。これらのサイトはマイクロソフトの管理下にあるものではなく、リンク先のサイトのコンテンツ、リンク先のサイトに含まれているリンク、または当該サイトの変更や更新について、マイクロソフトは一切責任を負いません。リンク先のサイトから受信した Web キャストまたはその他の形式での通信について、マイクロソフトは責任を負いません。マイクロソフトは受講者の便宜を図る目的でのみ、これらのリンクを提供します。また、リンクの掲載は、マイクロソフトが当該サイトまたは当該サイトに掲載されている製品を推奨していることを示唆するものではありません。

Copyright (c) Microsoft Corporation. All rights reserved.
