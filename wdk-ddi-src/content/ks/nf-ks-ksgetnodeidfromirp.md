---
UID: NF:ks.KsGetNodeIdFromIrp
title: KsGetNodeIdFromIrp function (ks.h)
description: The KsGetNodeIdFromIrp function returns the node ID of the node to which Irp was submitted.
old-location: stream\ksgetnodeidfromirp.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGetNodeIdFromIrp function"]
ms.keywords: KsGetNodeIdFromIrp, KsGetNodeIdFromIrp function [Streaming Media Devices], avfunc_dbc2812f-8011-40e6-8847-f7c3fc35b4b5.xml, ks/KsGetNodeIdFromIrp, stream.ksgetnodeidfromirp
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
 - KsGetNodeIdFromIrp
 - ks/KsGetNodeIdFromIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetNodeIdFromIrp
---

# KsGetNodeIdFromIrp function


## -description

The<b> KsGetNodeIdFromIrp </b>function returns the node ID of the node to which <i>Irp</i> was submitted.

## -parameters

### -param Irp [in]


A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure for which to determine the associated node ID. This IRP must have been sent to a file object corresponding to a filter, pin, or node.

## -returns

<b>KsGetNodeIdFromIrp </b>returns the ID of the node to which <i>Irp </i>was submitted. If <i>Irp</i> was instead submitted directly to the filter, it returns KSFILTER_NODE.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksaddirptocancelablequeue">KsAddIrpToCancelableQueue</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksdispatchirp">KsDispatchIrp</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksforwardirp">KsForwardIrp</a>
