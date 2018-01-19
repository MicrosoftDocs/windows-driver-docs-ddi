---
UID: NF:wdm.NtSetInformationTransactionManager
title: NtSetInformationTransactionManager function
author: windows-driver-content
description: Do not call this routine from kernel-mode code.
old-location: kernel\ntsetinformationtransactionmanager.htm
old-project: kernel
ms.assetid: a1e2f40f-5aea-4c8b-8692-95721ad4bc9d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: NtSetInformationTransactionManager
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
req.alt-api: NtSetInformationTransactionManager
req.alt-loc: wdm.h
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# NtSetInformationTransactionManager function



## -description
Do not call this routine from kernel-mode code.



## -syntax

````
NTSTATUS NtSetInformationTransactionManager(
  _In_opt_ HANDLE                                                   TmHandle,
  _In_     TRANSACTIONMANAGER_INFORMATION_CLASS                     TransactionManagerInformationClass,
  _In_     _reads_bytes_(TransactionManagerInformationLength) PVOID TransactionManagerInformation,
  _In_     ULONG                                                    TransactionManagerInformationLength
);
````


## -parameters

### -param TmHandle [in, optional]


### -param TransactionManagerInformationClass [in]


### -param TransactionManagerInformation [in]


### -param TransactionManagerInformationLength [in]


## -remarks
