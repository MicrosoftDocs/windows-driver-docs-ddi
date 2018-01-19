---
UID: NF:ks.KsCreateDefaultAllocator
title: KsCreateDefaultAllocator function
author: windows-driver-content
description: Given a validated IRP_MJ_CREATE request, the KsCreateDefaultAllocator function creates a default allocator that uses the specified memory pool and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the allocator using an internal dispatch table (KSDISPATCH_TABLE).
old-location: stream\kscreatedefaultallocator.htm
old-project: stream
ms.assetid: 79e7c92e-4c39-4c9f-a2d8-b83be08e3ec1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsCreateDefaultAllocator
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsCreateDefaultAllocator
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
req.typenames: 
---

# KsCreateDefaultAllocator function



## -description
Given a validated IRP_MJ_CREATE request, the <b>KsCreateDefaultAllocator</b> function creates a default allocator that uses the specified memory pool and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the allocator using an internal dispatch table (KSDISPATCH_TABLE).



## -syntax

````
NTSTATUS KsCreateDefaultAllocator(
  _In_ PIRP Irp
);
````


## -parameters

### -param Irp [in]

Specifies the IRP with the IRP_MJ_CREATE request being handled.


## -returns
The <b>KsCreateDefaultAllocator</b> function returns STATUS_SUCCESS if successful, or it returns an error if unsuccessful.


## -remarks
