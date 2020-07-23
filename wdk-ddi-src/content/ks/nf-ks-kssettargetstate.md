---
UID: NF:ks.KsSetTargetState
title: KsSetTargetState function (ks.h)
description: Sets the enabled state of a target device associated with the specified object header.
old-location: stream\kssettargetstate.htm
tech.root: stream
ms.assetid: 36f14936-8cc6-4488-aa0f-343e4fbb84e3
ms.date: 04/23/2018
keywords: ["KsSetTargetState function"]
ms.keywords: KsSetTargetState, KsSetTargetState function [Streaming Media Devices], ks/KsSetTargetState, ksfunc_7e05a5c0-2c82-4b20-a199-3955c61c6e40.xml, stream.kssettargetstate
f1_keywords:
 - "ks/KsSetTargetState"
 - "KsSetTargetState"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsSetTargetState
targetos: Windows
req.typenames: 
---

# KsSetTargetState function


## -description


Sets the enabled state of a target device associated with the specified object header.


## -parameters




### -param Header [in]

Points to a header previously allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedeviceheader">KsAllocateDeviceHeader</a>.


### -param TargetState [in]

Contains the new state of the target associated with this object header. This may be either KSTARGET_STATE_DISABLED or KSTARGET_STATE_ENABLED.


## -returns



None.




## -remarks



Assumes that such a target has been set with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kssettargetdeviceobject">KsSetTargetDeviceObject</a>. The target is initially disabled, and is ignored when recalculating stack depth. For WDM Streaming devices, this is called on a transition back to a Stop state, after having enabled the target and used <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksrecalculatestackdepth">KsRecalculateStackDepth</a> on a transition to Acquire state. This allows the stack depth to be minimized.



