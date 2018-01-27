---
UID: NF:wdm.TmInitializeTransactionManager
title: TmInitializeTransactionManager function
author: windows-driver-content
description: The TmInitializeTransactionManager routine initializes a transaction manager object.
old-location: kernel\tminitializetransactionmanager_.htm
old-project: kernel
ms.assetid: A44B4B93-4EC7-4FC3-B64F-BF1FF19D067E
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: TmInitializeTransactionManager routine [Kernel-Mode Driver Architecture], wdm/TmInitializeTransactionManager, kernel.tminitializetransactionmanager_, TmInitializeTransactionManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	Wdm.h
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
apiname: 
-	TmInitializeTransactionManager
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmInitializeTransactionManager function


## -description


The <b>TmInitializeTransactionManager</b> routine initializes a transaction manager object.


## -syntax


````
NTSTATUS TmInitializeTransactionManager (
  _In_     PRKTM             TransactionManager,
  _In_opt_ PCUNICODE_STRING  LogFileName,
  _In_     PGUID             TmId,
  _In_opt_ ULONG             CreateOptions
);
````


## -parameters




### -param TransactionManager [in]

A pointer to the transaction manager object to initialize.


### -param LogFileName [in, optional]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the path and file name of a <a href="https://msdn.microsoft.com/4da3cb49-dc20-4713-813b-ff458c99ab90">CLFS</a> log file stream associated with the transaction manager object. 


### -param TmId [in]

Specifies a pointer to a GUID that identifies  the name of the transaction manager object to initialize.


### -param CreateOptions [in, optional]

Optional object creation flags. The following table contains the available flags.
<table>
<tr>
<th>Option flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_VOLATILE

</td>
<td>
The transaction manager object will be volatile. Therefore, it will not use a log file.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_DEFAULT

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_SYSTEM_VOLUME

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_SYSTEM_HIVES

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_COMMIT_LOWEST

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_CORRUPT_FOR_RECOVERY

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
TRANSACTION_MANAGER_CORRUPT_FOR_PROGRESS

</td>
<td>
For internal use only.

</td>
</tr>
</table> 


## -returns


The <b>TmInitializeTransactionManager</b> routine  returns STATUS_SUCCESS if the operation succeeds.


