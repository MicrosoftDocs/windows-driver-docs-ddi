---
UID: NF:ks.KsDiscard
title: KsDiscard macro (ks.h)
description: The KsDiscard macro removes a given item from an object bag.
old-location: stream\ksdiscard.htm
tech.root: stream
ms.assetid: cbd1cd9b-c3bd-4827-88e6-4b80d6ba7320
ms.date: 04/23/2018
keywords: ["KsDiscard macro"]
ms.keywords: KsDiscard, KsDiscard function [Streaming Media Devices], avfunc_645e5574-6c6b-4336-87fe-fe777f7d1c91.xml, ks/KsDiscard, stream.ksdiscard
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsDiscard
 - ks/KsDiscard
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsDiscard
---

# KsDiscard macro


## -description

The **KsDiscard**macro removes a given item from an object bag.

## -parameters

### -param Object 

[in]
The item pointed to by *Pointer* is removed from the object bag associated with this object. Can be of type [KSDEVICE](./ns-ks-_ksdevice.md), [KSFILTERFACTORY](./ns-ks-_ksfilterfactory.md), [KSFILTER](./ns-ks-_ksfilter.md), or [KSPIN](./ns-ks-_kspin.md).

### -param Pointer 

[in]
A pointer to the item to be removed from the requested object's bag.

## -remarks

This macro wraps and assumes the return value of [KsRemoveItemFromObjectBag](./nf-ks-ksremoveitemfromobjectbag.md), which is **ULONG**.

This function is implemented as a C-style preprocessing macro in the *Ks.h* header.

**KsDiscard** calls **KsRemoveItemFromObjectBag**, passing the object bag associated with *Object* (*Object->Bag*), the item specified by *Pointer*, and **TRUE** for the *Free* parameter.

## -see-also

[KSDEVICE](./ns-ks-_ksdevice.md)

[KSFILTER](./ns-ks-_ksfilter.md)

[KSFILTERFACTORY](./ns-ks-_ksfilterfactory.md)

[KSPIN](./ns-ks-_kspin.md)

[KsRemoveItemFromObjectBag](./nf-ks-ksremoveitemfromobjectbag.md)