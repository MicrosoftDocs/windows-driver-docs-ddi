---
UID: NC:ks.PFNKSFASTHANDLER
title: PFNKSFASTHANDLER (ks.h)
description: KStrFastHandler is a driver-supplied routine that handles a property or method request without the creation of an IRP.
old-location: stream\kstrfasthandler.htm
tech.root: stream
ms.assetid: 9a72cdb5-2b57-4331-9836-82653732decf
ms.date: 04/23/2018
ms.keywords: KStrFastHandler, KStrFastHandler routine [Streaming Media Devices], PFNKSFASTHANDLER, ks/KStrFastHandler, ksfunc_e78a76eb-b3e6-4864-bae2-49536d3a9d52.xml, stream.kstrfasthandler
f1_keywords:
 - "ks/KStrFastHandler"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
- UserDefined
api_location:
- ks.h
api_name:
- KStrFastHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSFASTHANDLER callback function


## -description


<i>KStrFastHandler</i> is a driver-supplied routine that handles a property or method request without the creation of an IRP.


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



The minidriver provides an entry point for this routine in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksfastproperty_item">KSFASTPROPERTY_ITEM</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksfastmethod_item">KSFASTMETHOD_ITEM</a>.



