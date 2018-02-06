---
UID: NF:ntddk.PsCreateSiloContext
title: PsCreateSiloContext function
author: windows-driver-content
description: This routine creates an object that will be inserted in a Silo.
old-location: kernel\pscreatesilocontext.htm
old-project: kernel
ms.assetid: 54FD0308-7E40-40C7-BA3A-FF1EFFBE0DB6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsCreateSiloContext, ntddk/PsCreateSiloContext, kernel.pscreatesilocontext, PsCreateSiloContext routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsCreateSiloContext
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsCreateSiloContext function


## -description


This routine  creates an object that will be inserted in a <i>Silo</i>.


## -syntax


````
NTSTATUS PsCreateSiloContext(
  _In_     PESILO                                 Silo,
  _In_     ULONG                                  Size,
  _In_     POOL_TYPE                              PoolType,
  _In_opt_ SILO_CONTEXT_CLEANUP_CALLBACK          ContextCleanupCallback,
           _Outptr_result_bytebuffer_(Size) PVOID *ReturnedSiloContext
);
````


## -parameters




### -param Silo [in]

A pointer to a silo.  This parameter is required and it cannot be <b>NULL</b>.


### -param Size [in]

The size, in bytes, of the portion of the object defined by the caller.


### -param PoolType [in]

The type of pool to allocate from. This parameter is required and must be one of the following: <b>NonPagedPoolNx</b> or <b>PagedPool</b>.


### -param ContextCleanupCallback [in, optional]

A pointer to a <a href="..\ntddk\nc-ntddk-silo_context_cleanup_callback.md">SILO_CONTEXT_CLEANUP_CALLBACK</a> callback function. The function will be called when the returned object has zero references to it. This parameter is optional and can be <b>NULL</b>. 


### -param ReturnedSiloContext

A pointer to a caller-allocated variable that receives the address of the newly created object. 


## -returns


The following NT status codes are returned.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>
</td>
<td width="60%">
The routine encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pool type is not valid. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
</table> 


