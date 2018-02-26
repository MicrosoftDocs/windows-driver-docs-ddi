---
UID: NF:wdm.NtRenameTransactionManager
title: NtRenameTransactionManager function
author: windows-driver-content
description: The NtRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name.
old-location: kernel\ntrenametransactionmanager.htm
old-project: kernel
ms.assetid: 53baa93a-bd71-4975-86cc-51eb31c2f430
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , M, N, NtRenameTransactionManager, NtRenameTransactionManager routine [Kernel-Mode Driver Architecture], R, T, a, c, e, g, i, kernel.ntrenametransactionmanager, m, n, ntx_299b8860-3b7b-4bc7-8f33-c3805fd0a38f.xml, o, r, s, t, wdm/NtRenameTransactionManager"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	NtRenameTransactionManager
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# NtRenameTransactionManager function


## -description


The <b>NtRenameTransactionManager</b> routine changes the identity of the transaction manager object that is stored in the <a href="https://msdn.microsoft.com/4da3cb49-dc20-4713-813b-ff458c99ab90">CLFS</a> log file stream contained in the log file name.


## -syntax


````
NTSTATUS NtRenameTransactionManager(
  _In_ PUNICODE_STRING LogFileName,
  _In_ LPGUID          ExistingTransactionManagerGuid
);
````


## -parameters




### -param LogFileName [in]


### -param ExistingTransactionManagerGuid [in]


## -see-also


<a href="..\wdm\nf-wdm-tmrenametransactionmanager.md">TmRenameTransactionManager</a>


