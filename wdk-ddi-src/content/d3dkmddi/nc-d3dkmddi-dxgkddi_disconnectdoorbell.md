---
UID: NC:d3dkmddi.DXGKDDI_DISCONNECTDOORBELL
tech.root: display
title: DXGKDDI_DISCONNECTDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKDDI_DISCONNECTDOORBELL callback function.
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
 - DXGKDDI_DISCONNECTDOORBELL
f1_keywords:
 - DXGKDDI_DISCONNECTDOORBELL
 - d3dkmddi/DXGKDDI_DISCONNECTDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISCONNECTDOORBELL
---

## -description

The **DxgkDdiDisconnectDoorbell** function disconnects a previously connected doorbell object from a hardware queue.

## -parameters

### -param pArgs

[in/out] Pointer to a [**DXGKARG_DISCONNECTDOORBELL**](ns-d3dkmddi-dxgkarg_disconnectdoorbell.md) structure that describes the doorbell to disconnect.

## -returns

**DxgkDdiDisconnectDoorbell** must succeed and return STATUS_SUCCESS.

## -remarks

The OS calls **DxgkDdiDisconnectDoorbell** to unmap the physical doorbell location assigned to this doorbell. KMD should disconnect the hardware queue, doorbell physical address and engine, etc. The physical doorbell location can be assigned to some other logical doorbell object.

KMD should not destroy or free any other objects associated with **hDoorbell** because the doorbell object is not being destroyed and can be reconnected at a later point.

On return from this DDI call, *Dxgkrnl* does the following steps to disconnect the doorbell:

* Rotates the user-mode [**DoorbellCpuVirtualAddress**](../d3dkmthk/ns-d3dkmthk-d3dkmt_create_doorbell.md) to a dummy page so that UMD can no longer write to the physical doorbell location.
* Writes [D3DDDI_DOORBELL_STATUS_DISCONNECTED_RETRY](../d3dukmdt/ne-d3dukmdt-d3dddi_doorbellstatus.md) into **DoorbellStatusCpuVirtualAddress** so that UMD knows the doorbell is disconnected.

## -see-also

[**D3DDDI_DOORBELLSTATUS**](../d3dukmdt/ne-d3dukmdt-d3dddi_doorbellstatus.md)

[**D3DKMT_CREATE_DOORBELL**](../d3dkmthk/ns-d3dkmthk-d3dkmt_create_doorbell.md)

[**DXGKARG_DISCONNECTDOORBELL**](ns-d3dkmddi-dxgkarg_disconnectdoorbell.md)

[**DxgkDdiConnectDoorbell**](nc-d3dkmddi-dxgkddi_connectdoorbell.md)

[**DxgkDdiDisconnectDoorbellCB**](nc-d3dkmddi-dxgkcb_disconnectdoorbell.md)
