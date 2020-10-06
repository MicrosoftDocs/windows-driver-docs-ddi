---
UID: NS:ks.__unnamed_struct_70
title: KSFASTMETHOD_ITEM (ks.h)
description: Drivers provide a structure of type KSFASTMETHOD_ITEM to support fast I/O dispatching.
old-location: stream\ksfastmethod_item.htm
tech.root: stream
ms.assetid: 71e59c73-d77d-4b10-9d13-f5d21338eb94
ms.date: 04/23/2018
keywords: ["KSFASTMETHOD_ITEM structure"]
ms.keywords: "*PKSFASTMETHOD_ITEM, KSFASTMETHOD_ITEM, KSFASTMETHOD_ITEM structure [Streaming Media Devices], PKSFASTMETHOD_ITEM, PKSFASTMETHOD_ITEM structure pointer [Streaming Media Devices], ks-struct_1280212d-776c-4f9d-a00b-d880785c4cdf.xml, ks/KSFASTMETHOD_ITEM, ks/PKSFASTMETHOD_ITEM, stream.ksfastmethod_item"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
targetos: Windows
req.typenames: KSFASTMETHOD_ITEM, *PKSFASTMETHOD_ITEM
f1_keywords:
 - PKSFASTMETHOD_ITEM
 - ks/PKSFASTMETHOD_ITEM
 - KSFASTMETHOD_ITEM
 - ks/KSFASTMETHOD_ITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSFASTMETHOD_ITEM
---

# KSFASTMETHOD_ITEM structure


## -description

Drivers provide a structure of type KSFASTMETHOD_ITEM to support fast I/O dispatching.

## -struct-fields

### -field MethodId

Contains the identifier of the method and the flags describing the type of method.

### -field MethodHandler

Points to a driver-supplied <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksfasthandler">KStrFastHandler</a> routine for this method.

### -field MethodSupported

Set to <b>TRUE</b> if the method is supported, otherwise set to <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_item">KSMETHOD_ITEM</a>



<a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksfasthandler">KStrFastHandler</a>