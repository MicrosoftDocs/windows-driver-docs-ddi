---
UID: NF:wdm.TmInitializeTransactionManager
title: TmInitializeTransactionManager function (wdm.h)
description: The TmInitializeTransactionManager routine initializes a transaction manager object.
old-location: kernel\tminitializetransactionmanager_.htm
tech.root: kernel
ms.assetid: A44B4B93-4EC7-4FC3-B64F-BF1FF19D067E
ms.date: 04/30/2018
ms.keywords: TmInitializeTransactionManager, TmInitializeTransactionManager , TmInitializeTransactionManager routine [Kernel-Mode Driver Architecture], kernel.tminitializetransactionmanager_, wdm/TmInitializeTransactionManager
ms.topic: function
f1_keywords:
 - "wdm/TmInitializeTransactionManager"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wdm.h
- Ext-MS-Win-ntos-tm-l1-1-0.dll
- tm.sys
api_name:
- TmInitializeTransactionManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmInitializeTransactionManager function


## -description


The <b>TmInitializeTransactionManager</b> routine initializes a transaction manager object.


## -parameters




### -param TransactionManager [in]

A pointer to the transaction manager object to initialize.


### -param LogFileName [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the path and file name of a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-clfs-library">CLFS</a> log file stream associated with the transaction manager object. 


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



