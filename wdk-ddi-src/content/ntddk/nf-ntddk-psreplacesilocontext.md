---
UID: NF:ntddk.PsReplaceSiloContext
title: PsReplaceSiloContext function
author: windows-driver-content
description: This routine inserts an object in a Silo.
old-location: kernel\psreplacesilocontext.htm
old-project: kernel
ms.assetid: C2A8F7FF-7DBA-4725-A64C-7F694C8001C0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsReplaceSiloContext
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
req.alt-api: PsReplaceSiloContext
req.alt-loc: ntddk.h
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
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsReplaceSiloContext function



## -description
This routine inserts an object in a <i>Silo</i>.



## -syntax

````
NTSTATUS PsReplaceSiloContext(
  _In_ PESILO                              Silo,
  _In_ ULONG                               ContextSlot,
  _In_ PVOID                               NewSiloContext,
       _Outptr_opt_result_maybenull_ PVOID *OldSiloContext
);
````


## -parameters

### -param Silo [in]

A pointer to a silo.  This parameter is required and it cannot be <b>NULL</b>.


### -param ContextSlot [in]

A slot allocated by the <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine. 


### -param NewSiloContext [in]

A pointer to the object created by the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine. The object must be created using the same silo pointer as the one specified in this routine. This parameter is required and it cannot be <b>NULL</b>. 


### -param OldSiloContext [optional]

A pointer to a caller-allocated variable that receives the address of the existing object. This parameter is optional and can be <b>NULL</b>. The address that the parameter receives can be <b>NULL</b>. 


## -returns
The following NT status codes are returned.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>There are no resources in the system to perform the insert. This is an error code. 
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The slot is read-only and it cannot be modified. This is an error code.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

 


## -remarks
A successful call to <b>PsReplaceSiloContext</b> increments the reference count on <i>NewSiloContext</i>. If <b>PsReplaceSiloContext</b> fails, the reference count remains unchanged. In either case, the caller of <b>PsReplaceSiloContext</b> must call <a href="..\ntddk\nf-ntddk-psdereferencesilocontext.md">PsDereferenceSiloContext</a> to decrement the <b>PsReplaceSiloContext</b> object. If <b>PsReplaceSiloContext</b> fails and if the <i>OldSiloContext</i> parameter is not <b>NULL</b> and does not point to <b>NULL</b> then <b>NULL</b> is a referenced pointer. After the routine completes, the caller must call <b>PsDereferenceSiloContext</b> to decrement the object that the <b>NULL</b> parameter points to. </p>