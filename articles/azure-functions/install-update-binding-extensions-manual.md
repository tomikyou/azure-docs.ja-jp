---
title: Azure Functions バインド拡張機能を手動でインストールまたは更新する
description: デプロイした関数アプリに Azure Functions バインド拡張機能をインストールまたは更新する方法について説明します。
ms.topic: reference
ms.date: 09/26/2018
ms.openlocfilehash: e8716f691a5d19ddac7fece47c423e1f7787b9db
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "75768862"
---
# <a name="manually-install-or-update-azure-functions-binding-extensions-from-the-portal"></a>Azure Functions バインド拡張機能をポータルから手動でインストールまたは更新する

バージョン 2.x 以降、Azure Functions ランタイムは、トリガーとバインドのコードを実装するためにバインド拡張機能を使用します。 バインド拡張機能は、NuGet パッケージで提供されます。 拡張機能を登録するには、パッケージをインストールします。 関数を開発しているときに、バインド拡張機能をインストールする方法は、開発環境に応じて異なります。 詳細については、トリガーとバインドに関する記事の「[バインド拡張機能を登録する](./functions-bindings-register.md)」をご覧ください。

ときおり、バインド拡張機能を Azure portal から手動でインストールまたは更新することが必要になる場合があります。 たとえば、登録済みのバインドを新しいバージョンに更新する必要がある場合があります。 また、ポータルの **[統合]** タブにはインストールできない、サポート対象のバインドを登録する必要がある場合もあります。

## <a name="install-a-binding-extension"></a>バインド拡張機能をインストールする

拡張機能をポータルから手動でインストールまたは更新するには、次の手順を使用します。

1. [Azure portal](https://portal.azure.com) で、ご使用の関数アプリを検索し、選択します。 **[概要]** タブを選択し、 **[停止]** を選択します。  関数アプリを停止すると、ファイルのロックが解除されるため、変更を加えられるようになります。

1. **[プラットフォーム機能]** タブを選択し、 **[開発ツール]** の下で **[高度なツール (Kudu)]** を選択します。 Kudu エンドポイント (`https://<APP_NAME>.scm.azurewebsites.net/`) が新しいウィンドウで開きます。

1. Kudu ウィンドウで、 **[デバッグ コンソール]**  >  **[CMD]** の順に選択します。  

1. コマンド ウィンドウで、`D:\home\site\wwwroot` に移動し、`bin` の横にある削除アイコンを選択してフォルダーを削除します。 **[OK]** を選択して削除を確定します。

1. `extensions.csproj` ファイルの隣にある編集アイコンを選択します。このファイルでは、関数アプリのバインド拡張機能を定義します。 プロジェクト ファイルがオンライン エディターで開きます。

1. **ItemGroup** 内の **PackageReference** 項目に必要な追加と更新を行い、 **[保存]** を選択します。 現在サポートされているパッケージ バージョンの一覧は、「[What packages do I need? (必要なパッケージ)](https://github.com/Azure/azure-functions-host/wiki/Updating-your-function-app-extensions#what-nuget-packages-do-i-need)」という wiki 記事をご覧ください。 3 つの Azure Storage バインドすべてには Microsoft.Azure.WebJobs.Extensions.Storage パッケージが必要です。

1. `wwwroot` フォルダーから次のコマンドを実行して、`bin` フォルダーにある参照アセンブリをリビルドします。

    ```cmd
    dotnet build extensions.csproj -o bin --no-incremental --packages D:\home\.nuget
    ```

1. ポータルの **[概要]** タブに戻り、 **[開始]** を選択して関数アプリを再起動します。

## <a name="next-steps"></a>次のステップ

> [!div class="nextstepaction"]
> [Azure Functions のトリガーとバインドの詳細情報](functions-triggers-bindings.md)
