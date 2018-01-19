---
UID: NC:ks.PFNKSFASTHANDLER
title: PFNKSFASTHANDLER
author: windows-driver-content
description: KStrFastHandler is a driver-supplied routine that handles a property or method request without the creation of an IRP.
old-location: stream\kstrfasthandler.htm
old-project: stream
ms.assetid: 9a72cdb5-2b57-4331-9836-82653732decf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrFastHandler
req.alt-loc: ks.h
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
req.typenames: KEYWORDSELECTOR
---

# PFNKSFASTHANDLER callback



## -description
<i>KStrFastHandler</i> is a driver-supplied routine that handles a property or method request without the creation of an IRP.



## -prototype

````
PFNKSFASTHANDLER KStrFastHandler;

BOOLEAN KStrFastHandler(
  _In_    PFILE_OBJECT     FileObject,
  _In_    PKSIDENTIFIER    Request,
  _In_    ULONG            RequestLength,
  _Inout_ PVOID            Data,
  _In_    ULONG            DataLength,
  _Out_   PIO_STATUS_BLOCK IoStatus
)
{ ... }
````


## -parameters

### -param FileObject [in]

Specifies the file object on which the request was made.


### -param Request [in]

Specifies the original property parameter. This will always be on FILE_LONG_ALIGNMENT, but cannot be on FILE_QUAD_ALIGNMENT.


### -param RequestLength [in]

Specifies the length indicated by the caller of the property parameter.


### -param Data [in, out]

Specifies the original unaligned data parameter.


### -param DataLength [in]

Specifies the length indicated by the caller of the data parameter.


### -param IoStatus [out]

Specifies an aligned structure that is used to return error status and information. This information is then copied to the original I/O status structure on completion.


## -returns
<i>KStrFastHandler</i> returns <b>TRUE</b> if the call was handled. If the call was not handled, it returns <b>FALSE</b> and an IRP is generated to handle the request.


## -remarks
The minidriver provides an entry point for this routine in <a href="..\ks\ns-ks-ksfastproperty_item.md">KSFASTPROPERTY_ITEM</a> or <a href="..\ks\ns-ks-ksfastmethod_item.md">KSFASTMETHOD_ITEM</a>.</p>