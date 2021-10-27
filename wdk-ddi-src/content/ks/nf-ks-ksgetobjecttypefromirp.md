---
UID: NF:ks.KsGetObjectTypeFromIrp
title: KsGetObjectTypeFromIrp function (ks.h)
description: The KsGetObjectTypeFromIrp function returns the AVStream object type that is associated with a given IRP.
old-location: stream\ksgetobjecttypefromirp.htm
tech.root: stream
ms.date: 04/12/2021
keywords: ["KsGetObjectTypeFromIrp function"]
ms.keywords: KsGetObjectTypeFromIrp, KsGetObjectTypeFromIrp function [Streaming Media Devices], avfunc_4021d1e6-6dcd-4c59-8863-0d0b5a8e922f.xml, ks/KsGetObjectTypeFromIrp, stream.ksgetobjecttypefromirp
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGetObjectTypeFromIrp
 - ks/KsGetObjectTypeFromIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetObjectTypeFromIrp
---

# KsGetObjectTypeFromIrp function

## -description

The **KsGetObjectTypeFromIrp** function returns the AVStream object type that is associated with a given IRP.

## -parameters

### -param Irp [in]


A pointer to the [IRP](../wdm/ns-wdm-_irp.md) structure for which to find the associated AVStream object type.

## -returns

**KsGetObjectTypeFromIrp** returns the type of AVStream object associated with the given IRP as a [KSOBJECTTYPE](./ne-ks-ksobjecttype.md) enumeration. This is one of the following: **KsObjectTypeDevice**, **KsObjectTypeFilterFactory**, **KsObjectTypeFilter**, **KsObjectTypePin**.

## -remarks

The **KsGetObjectTypeFromIrp** function does not check that the I/O request packet (IRP) is associated with a KS object. If it is not, this may result in a memory access error. Driver developers should consider using structured exception handling to catch a possible exception.

## -see-also

[IRP](../wdm/ns-wdm-_irp.md)

[KsAddIrpToCancelableQueue](./nf-ks-ksaddirptocancelablequeue.md)

[KsDispatchIrp](./nf-ks-ksdispatchirp.md)

[KsForwardIrp](./nf-ks-ksforwardirp.md)
