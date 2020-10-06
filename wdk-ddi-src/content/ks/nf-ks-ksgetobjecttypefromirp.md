---
UID: NF:ks.KsGetObjectTypeFromIrp
title: KsGetObjectTypeFromIrp function (ks.h)
description: The KsGetObjectTypeFromIrp function returns the AVStream object type that is associated with a given IRP.
old-location: stream\ksgetobjecttypefromirp.htm
tech.root: stream
ms.assetid: 4fe45811-a823-4cc6-bdc4-a1f2ac892d37
ms.date: 04/23/2018
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

The<b> KsGetObjectTypeFromIrp</b> function returns the AVStream object type that is associated with a given IRP.

## -parameters

### -param Irp 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure for which to find the associated AVStream object type.

## -returns

<b>KsGetObjectTypeFromIrp</b> returns the type of AVStream object associated with the given IRP as a <a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksobjecttype">KSOBJECTTYPE</a> enumeration. This is one of the following: <b>KsObjectTypeDevice</b>, <b>KsObjectTypeFilterFactory</b>, <b>KsObjectTypeFilter</b>, <b>KsObjectTypePin</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksaddirptocancelablequeue">KsAddIrpToCancelableQueue</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksdispatchirp">KsDispatchIrp</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksforwardirp">KsForwardIrp</a>