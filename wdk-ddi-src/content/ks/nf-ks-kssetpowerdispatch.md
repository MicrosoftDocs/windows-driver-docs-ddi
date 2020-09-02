---
UID: NF:ks.KsSetPowerDispatch
title: KsSetPowerDispatch function (ks.h)
description: Sets the power dispatch function to be called when the driver object receives an IRP_MJ_POWER IRP.
old-location: stream\kssetpowerdispatch.htm
tech.root: stream
ms.assetid: 77ceaebe-ded1-4fbb-bc10-593ff62fcbe2
ms.date: 04/23/2018
keywords: ["KsSetPowerDispatch function"]
ms.keywords: KsSetPowerDispatch, KsSetPowerDispatch routine [Streaming Media Devices], ks/KsSetPowerDispatch, ksfunc_b561e4ba-dadd-4e9c-a8e3-1d9b182cdd4f.xml, stream.kssetpowerdispatch
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsSetPowerDispatch
 - ks/KsSetPowerDispatch
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsSetPowerDispatch
---

# KsSetPowerDispatch function


## -description

Sets the power dispatch function to be called when the driver object receives an <b>IRP_MJ_POWER</b> IRP. This is only effective if <b>KsDefaultDispatchPower</b> is called to dispatch or complete power IRPs.

This has the effect of adding this object header to a list of object headers that have power dispatch routines to execute. The head of this list is kept by the device header. Assumes that the caller has previously allocated a device header on the underlying Device Object with <b>KsAllocateDeviceHeader</b>.

## -parameters

### -param Header 

[in]
Points to a header previously allocated by <b>KsAllocateObjectHeader</b>.

### -param PowerDispatch 

[in, optional]
Optionally contains the power dispatch function that will be called, or <b>NULL</b> if the function is to be removed from the list of functions being called. This function must not complete the power IRP sent. The return value of this function must be STATUS_SUCCESS. <b>KsSetPowerDispatch</b> can be called while executing this power dispatch routine if the purpose is to manipulate this list entry only. Manipulating other list entries may confuse the current enumeration.

### -param PowerContext 

[in, optional]
Optionally contains the context parameter to pass to the power dispatch function.

## -returns

None

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscontext_dispatch">KStrContextDispatch</a>

