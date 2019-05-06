---
UID: NF:ks.KsDiscard
title: KsDiscard macro (ks.h)
description: The KsDiscard macro removes a given item from an object bag.
old-location: stream\ksdiscard.htm
tech.root: stream
ms.assetid: cbd1cd9b-c3bd-4827-88e6-4b80d6ba7320
ms.date: 04/23/2018
ms.keywords: KsDiscard, KsDiscard function [Streaming Media Devices], avfunc_645e5574-6c6b-4336-87fe-fe777f7d1c91.xml, ks/KsDiscard, stream.ksdiscard
ms.topic: macro
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDiscard macro

## -description

The **KsDiscard**macro removes a given item from an object bag.

## -parameters

### -param Object [in]

The item pointed to by *Pointer* is removed from the object bag associated with this object. Can be of type [KSDEVICE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice), [KSFILTERFACTORY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilterfactory), [KSFILTER](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter), or [KSPIN](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin).

### -param Pointer [in]

A pointer to the item to be removed from the requested object's bag.

## -remarks

This macro wraps and assumes the return value of [KsRemoveItemFromObjectBag](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksremoveitemfromobjectbag), which is **ULONG**.

This function is implemented as a C-style preprocessing macro in the *Ks.h* header.

**KsDiscard** calls **KsRemoveItemFromObjectBag**, passing the object bag associated with *Object* (*Object->Bag*), the item specified by *Pointer*, and **TRUE** for the *Free* parameter.

## -see-also

[KSDEVICE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice)

[KSFILTER](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter)

[KSFILTERFACTORY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilterfactory)

[KSPIN](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin)

[KsRemoveItemFromObjectBag](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksremoveitemfromobjectbag)
