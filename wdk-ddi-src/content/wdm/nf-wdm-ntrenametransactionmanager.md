---
UID: NF:wdm.NtRenameTransactionManager
title: NtRenameTransactionManager function (wdm.h)
description: The NtRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name.
old-location: kernel\ntrenametransactionmanager.htm
tech.root: kernel
ms.assetid: 53baa93a-bd71-4975-86cc-51eb31c2f430
ms.date: 04/30/2018
keywords: ["NtRenameTransactionManager function"]
ms.keywords: NtRenameTransactionManager, NtRenameTransactionManager routine [Kernel-Mode Driver Architecture], kernel.ntrenametransactionmanager, ntx_299b8860-3b7b-4bc7-8f33-c3805fd0a38f.xml, wdm/NtRenameTransactionManager
f1_keywords:
 - "wdm/NtRenameTransactionManager"
 - "NtRenameTransactionManager"
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- NtRenameTransactionManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtRenameTransactionManager function


## -description


The <b>NtRenameTransactionManager</b> routine changes the identity of the transaction manager object that is stored in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-clfs-library">CLFS</a> log file stream contained in the log file name.


## -parameters




### -param LogFileName [in]


### -param ExistingTransactionManagerGuid [in]


## -see-also


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-tmrenametransactionmanager">TmRenameTransactionManager</a>


