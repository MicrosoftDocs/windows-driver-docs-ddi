---
UID: NF:ntddk.IoGetTransactionParameterBlock
title: IoGetTransactionParameterBlock function
author: windows-driver-content
description: The IoGetTransactionParameterBlock routine returns the transaction parameter block for a transacted file operation.
old-location: ifsk\iogettransactionparameterblock.htm
old-project: ifsk
ms.assetid: f07919f8-644f-43a4-98d7-d0f1a91d405d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoGetTransactionParameterBlock, IoGetTransactionParameterBlock routine [Installable File System Drivers], ifsk.iogettransactionparameterblock, ioref_4bce32be-89e0-4b69-9e44-a4b619588c79.xml, ntddk/IoGetTransactionParameterBlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista and later
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetTransactionParameterBlock
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetTransactionParameterBlock function


## -description


The <b>IoGetTransactionParameterBlock</b> routine returns the transaction parameter block for a transacted file operation. 


## -parameters




### -param FileObject [in]

A pointer to a file object for the file. 


## -returns



The <b>IoGetTransactionParameterBlock</b> routine returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556863">TXN_PARAMETER_BLOCK</a> structure if the file operation is transacted, otherwise it returns <b>NULL</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556863">TXN_PARAMETER_BLOCK</a>
 

 

