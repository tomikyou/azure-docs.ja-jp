---
title: VHD からスナップショットを作成して、同一のマネージド ディスクを複数作成する - PowerShell サンプル
description: Azure PowerShell サンプル スクリプト - VHD からスナップショットを作成してまったく同じ複数のマネージド ディスクを短時間で作成する
services: virtual-machines-linux
documentationcenter: storage
author: ramankumarlive
manager: kavithag
tags: azure-service-management
ms.assetid: ''
ms.service: virtual-machines-linux
ms.topic: sample
ms.tgt_pltfrm: vm-linux
ms.workload: infrastructure
ms.date: 06/05/2017
ms.author: ramankum
ms.openlocfilehash: b163b5a1aad343382b9b2d22a91c1b07078c14df
ms.sourcegitcommit: 58faa9fcbd62f3ac37ff0a65ab9357a01051a64f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "81459714"
---
# <a name="create-a-snapshot-from-a-vhd-to-create-multiple-identical-managed-disks-in-small-amount-of-time-with-powershell"></a>PowerShell で VHD からスナップショットを作成してまったく同じ複数のマネージド ディスクを短時間で作成する

このスクリプトでは、同じまたは別のサブスクリプションのストレージ アカウントに VHD ファイルからスナップショットを作成します。 sysprep された汎用的な VHD ではなく特殊化された VHD をインポートしてスナップショットを作成し、そのスナップショットを使ってまったく同じ複数のマネージド ディスクを短時間で作成するには、このスクリプトを使います。 また、データ VHD をスナップショットにインポートし、そのスナップショットを使って複数のマネージド ディスクを短時間で作成する際にも使うことができます。

[!INCLUDE [quickstarts-free-trial-note](../../../includes/quickstarts-free-trial-note.md)]


 

## <a name="sample-script"></a>サンプル スクリプト

[!code-powershell[main](../../../powershell_scripts/virtual-machine/create-snapshots-from-vhd-in-different-subscription/create-snapshots-from-vhd-in-different-subscription.ps1 "Create snapshot from VHD")]

## <a name="script-explanation"></a>スクリプトの説明

このスクリプトでは、以下のコマンドを使って別のサブスクリプションに VHD からマネージド ディスクを作成します。 表内の各コマンドは、それぞれのドキュメントにリンクされています。

| command | メモ |
|---|---|
| [New-AzDiskConfig](https://docs.microsoft.com/powershell/module/az.compute/New-AzDiskConfig) | ディスクの作成に使用するディスク構成を作成します。 この構成には、ストレージの種類、場所、親 VHD が格納されているストレージ アカウントのリソース ID、親 VHD の URI が含まれます。 |
| [New-AzDisk](https://docs.microsoft.com/powershell/module/az.compute/New-AzDisk) | パラメーターとして渡されたディスク構成、ディスク名、リソース グループ名を使ってディスクを作成します。 |

## <a name="next-steps"></a>次のステップ

[スナップショットからマネージド ディスクを作成する](virtual-machines-linux-powershell-sample-create-managed-disk-from-snapshot.md?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json)

Azure PowerShell モジュールの詳細については、[Azure PowerShell のドキュメント](/powershell/azure/overview)を参照してください。

その他の仮想マシン用の PowerShell サンプル スクリプトは、[Azure Linux VM のドキュメント](../linux/powershell-samples.md?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json)にあります。
