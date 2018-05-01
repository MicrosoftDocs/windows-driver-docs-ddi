---
UID: NF:wdm.TmRenameTransactionManager
title: TmRenameTransactionManager function
author: windows-driver-content
description: The TmRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name.
old-location: kernel\tmrenametransactionmanager_.htm
old-project: kernel
ms.assetid: B4124FF4-50CC-474A-B42F-17BCF698AB59
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: TmRenameTransactionManager, TmRenameTransactionManager , TmRenameTransactionManager routine [Kernel-Mode Driver Architecture], kernel.tmrenametransactionmanager_, wdm/TmRenameTransactionManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Wdm.h
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
api_name:
-	TmRenameTransactionManager
product: Windows
targetos: Windows
req.typenames: 
---

# TmRenameTransactionManager function


## -description


The <b>TmRenameTransactionManager</b> routine changes the identity of the transaction manager object that is stored in the <a href="https://msdn.microsoft.com/4da3cb49-dc20-4713-813b-ff458c99ab90">CLFS</a> log file stream contained in the log file name.
<div class="alert"><b>Warning</b>  Changing the identity of the transaction manger object might break any cross-log transactional links that may exist.</div><div> </div>

## -parameters




### -param LogFileName [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the path and file name of a <a href="https://msdn.microsoft.com/4da3cb49-dc20-4713-813b-ff458c99ab90">CLFS</a> log file stream to be associated with the transaction manager object.


### -param ExistingTransactionManagerGuid [in]

A pointer to a GUID structure that represents the current name of the transaction manager object.


## -returns



The <b>TmRenameTransactionManager</b> routine returns an NTSTATUS value. If the routine fails, it returns one of the following error codes:



