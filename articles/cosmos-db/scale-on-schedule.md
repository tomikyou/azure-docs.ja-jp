---
title: Azure Functions のタイマーを使用してスケジュールに従って Azure Cosmos DB をスケーリングする
description: PowerShell と Azure Functions を使用して、Azure Cosmos DB のスループットの変更をスケーリングする方法について説明します。
author: markjbrown
ms.service: cosmos-db
ms.topic: conceptual
ms.date: 01/13/2020
ms.author: mjbrown
ms.openlocfilehash: 68ba40ea212c061fa5c8bbddc47ea0dfc6d8caa4
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "75934948"
---
# <a name="scale-azure-cosmos-db-throughput-by-using-azure-functions-timer-trigger"></a>Azure Functions のタイマー トリガーを使用して Azure Cosmos DB のスループットをスケーリングする

Azure Cosmos アカウントのパフォーマンスは、要求ユニット/秒 (RU/秒) で表されるプロビジョニングされているスループットの量に基づいています。 プロビジョニングの粒度は 1 秒であり、1 時間あたりの最大 RU/秒に基づいて課金されます。 容量がプロビジョニングされるというモデルによって、予測可能で一貫性のあるスループットをサービスが提供でき、待機時間が短くなり、可用性が高くなります。 ほとんどの運用ワークロードがこれらの機能を備えています。 ただし、Azure Cosmos DB が業務時間中にのみ使用される開発およびテスト環境では、朝にスループットをスケールアップし、業務時間後の夕方にスケールダウンして戻すことができます。

スループットは、コア (SQL) API アカウントに対して [Azure Resource Manager テンプレート](resource-manager-samples.md)、[Azure CLI](cli-samples.md)、および [PowerShell](powershell-samples-sql.md) を使用して、または言語固有の Azure Cosmos DB SDK を使用して設定できます。 Resource Manager テンプレート、Azure CLI、または PowerShell を使用する利点は、これらがすべての Azure Cosmos DB モデル API をサポートしていることです。

## <a name="throughput-scheduler-sample-project"></a>スループット スケジューラのサンプル プロジェクト

スケジュールに従って Azure Cosmos DB をスケーリングするプロセスを簡素化するために、[Azure Cosmos スループット スケジューラ](https://github.com/Azure-Samples/azure-cosmos-throughput-scheduler)と呼ばれるサンプル プロジェクトを作成しました。 このプロジェクトは、"ScaleUpTrigger" と "ScaleDownTrigger" の 2 つのタイマー トリガーを持つ Azure Functions アプリです。 これらトリガーは、各トリガーの `resources.json` ファイルで定義された各リソースに関するスループットを設定する PowerShell スクリプトを実行します。 ScaleUpTrigger は午前 8 時 (UTC) に実行されるように構成され、ScaleDownTrigger は午後 6 時 (UTC) に実行されるように構成されています。これらの時刻は、各トリガーの `function.json` ファイル内で容易に更新できます。

このプロジェクトをローカルで複製し、スケールアップおよびスケールダウンする Azure Cosmos DB リソースと実行されるスケジュールを指定するように変更できます。 後で、それを Azure サブスクリプションにデプロイし、"Azure Cosmos DB オペレーター" ロールの[ロールベースのアクセス制御](role-based-access-control.md) (RBAC) アクセス許可を持つマネージド サービス ID を使用してセキュリティで保護することにより、Azure Cosmos アカウントでスループットを設定できます。

## <a name="next-steps"></a>次の手順

- 詳細については、[Azure Cosmos DB スループット スケジューラ](https://github.com/Azure-Samples/azure-cosmos-throughput-scheduler)からサンプルをダウンロードしてください。
