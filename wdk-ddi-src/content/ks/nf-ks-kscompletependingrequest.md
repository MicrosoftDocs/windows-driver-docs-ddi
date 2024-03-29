---
UID: NF:ks.KsCompletePendingRequest
title: KsCompletePendingRequest function (ks.h)
description: The KsCompletePendingRequest function is used to complete an I/O request in response to which an AVStream dispatch function previously returned STATUS_PENDING.
old-location: stream\kscompletependingrequest.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsCompletePendingRequest function"]
ms.keywords: KsCompletePendingRequest, KsCompletePendingRequest function [Streaming Media Devices], avfunc_e01e61fc-ec10-4781-aee2-0aa7e24ca31a.xml, ks/KsCompletePendingRequest, stream.kscompletependingrequest
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsCompletePendingRequest
 - ks/KsCompletePendingRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsCompletePendingRequest
---

# KsCompletePendingRequest function


## -description

The<b> KsCompletePendingRequest</b> function is used to complete an I/O request in response to which an AVStream dispatch function previously returned STATUS_PENDING.

## -parameters

### -param Irp [in]


A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure that must be completed; this is passed in the dispatch function that returned a STATUS_PENDING.

## -remarks

If the dispatch function in question does not pass an IRP, it <b>cannot</b> return STATUS_PENDING. Minidrivers should set <b>IRP.IoStatus.Status</b> before calling this function.

<b>KsCompletePendingRequest</b> can be used for PnP dispatch functions in the device dispatch table or filter creation and closure requests. Dispatch functions that return STATUS_PENDING must call this function when they complete the request.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch">KSFILTER_DISPATCH</a>
