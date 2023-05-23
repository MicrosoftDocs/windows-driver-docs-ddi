---
UID: NC:d3dkmddi.DXGKCB_DISCONNECTDOORBELL
tech.root: display
title: DXGKCB_DISCONNECTDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKCB_DISCONNECTDOORBELL callback function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_FUTURE
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_DISCONNECTDOORBELL
f1_keywords:
 - DXGKCB_DISCONNECTDOORBELL
 - d3dkmddi/DXGKCB_DISCONNECTDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKCB_DISCONNECTDOORBELL
---

## -description

KMD calls this **DxgkCbDisconnectDoorbell** function to notify *Dxgkrnl* that KMD needs to disconnect a previously connected doorbell object from a hardware queue.

## -parameters

### -param pArgs

[in] Pointer to a [**DXGKARGCB_DISCONNECTDOORBELL**](ns-d3dkmddi-dxgkargcb_disconnectdoorbell.md) structure that describes the doorbell to disconnect.

## -returns

**DxgkCbDisconnectDoorbell** returns STATUS_INVALID_PARAMETER if *Dxgkrnl* can't find the associated doorbell object for **hHwQueue**. In all other cases this function succeeds, even when the doorbell is already disconnected.

## -remarks

KMD calls this function to notify *Dxgkrnl* when it needs to disconnect a doorbell. KMD should consider the physical doorbell address to be disconnected only after return from this callback.

*Dxgkrnl* unmaps the virtual addresses and marks the doorbell as disconnected. Specifically, *Dxgkrnl* does the following steps to disconnect the doorbell:

* Rotates the user-mode [**DoorbellCpuVirtualAddress**](../d3dkmthk/ns-d3dkmthk-d3dkmt_create_doorbell.md) to a dummy page so that UMD can no longer write to the physical doorbell location.
* Writes the **DisconnectReason** into **DoorbellStatusCpuVirtualAddress** so that UMD knows that the doorbell is disconnected and the reason why.

## -see-also

[**DXGKARGCB_DISCONNECTDOORBELL**](ns-d3dkmddi-dxgkargcb_disconnectdoorbell.md)

[**DxgkDdiConnectDoorbell**](nc-d3dkmddi-dxgkddi_connectdoorbell.md)
