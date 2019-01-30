---
UID: NF:ntddk.PsReplaceSiloContext
title: PsReplaceSiloContext function (ntddk.h)
description: This routine inserts an object in a Silo.
old-location: kernel\psreplacesilocontext.htm
tech.root: kernel
ms.assetid: C2A8F7FF-7DBA-4725-A64C-7F694C8001C0
ms.date: 04/30/2018
ms.keywords: PsReplaceSiloContext, PsReplaceSiloContext routine [Kernel-Mode Driver Architecture], kernel.psreplacesilocontext, ntddk/PsReplaceSiloContext
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsReplaceSiloContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsReplaceSiloContext function


## -description


This routine inserts an object in a <i>Silo</i>.


## -parameters




### -param Silo [in]

A pointer to a silo.  This parameter is required and it cannot be <b>NULL</b>.


### -param ContextSlot [in]

A slot allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735056">PsAllocSiloContextSlot</a> routine. 


### -param NewSiloContext [in]

A pointer to the object created by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735058">PsCreateSiloContext</a> routine. The object must be created using the same silo pointer as the one specified in this routine. This parameter is required and it cannot be <b>NULL</b>. 


### -param OldSiloContext [optional]

A pointer to a caller-allocated variable that receives the address of the existing object. This parameter is optional and can be <b>NULL</b>. The address that the parameter receives can be <b>NULL</b>. 


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
There are no resources in the system to perform the insert. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The slot is read-only and it cannot be modified. This is an error code.

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
 




## -remarks



A successful call to <b>PsReplaceSiloContext</b> increments the reference count on <i>NewSiloContext</i>. If <b>PsReplaceSiloContext</b> fails, the reference count remains unchanged. In either case, the caller of <b>PsReplaceSiloContext</b> must call <a href="https://msdn.microsoft.com/library/windows/hardware/mt735059">PsDereferenceSiloContext</a> to decrement the <b>PsReplaceSiloContext</b> object. If <b>PsReplaceSiloContext</b> fails and if the <i>OldSiloContext</i> parameter is not <b>NULL</b> and does not point to <b>NULL</b> then <b>NULL</b> is a referenced pointer. After the routine completes, the caller must call <b>PsDereferenceSiloContext</b> to decrement the object that the <b>NULL</b> parameter points to. 



