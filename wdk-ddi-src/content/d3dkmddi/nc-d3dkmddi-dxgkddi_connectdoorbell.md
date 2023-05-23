---
UID: NC:d3dkmddi.DXGKDDI_CONNECTDOORBELL
tech.root: display
title: DXGKDDI_CONNECTDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKDDI_CONNECTDOORBELL callback function.
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
 - DXGKDDI_CONNECTDOORBELL
f1_keywords:
 - DXGKDDI_CONNECTDOORBELL
 - d3dkmddi/DXGKDDI_CONNECTDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CONNECTDOORBELL
---

## -description

**DxgkDdiConnectDoorbell** connects (or reconnects) a [previously created doorbell object](ns-d3dkmddi-dxgkarg_createdoorbell.md) to a hardware queue.

## -parameters

### -param pArgs

[in/out] Pointer to a [**DXGKARG_CONNECTDOORBELL**](ns-d3dkmddi-dxgkarg_connectdoorbell.md) structure that describes the doorbell to connect.

## -returns

**DxgkDdiConnectDoorbell** returns STATUS_SUCCESS if KMD was able to successfully connect its doorbell object to the specified hardware queue. This call should not typically fail; however, a returned failure code would be from GPU lost or stopped kinds of irrecoverable scenarios.

## -remarks

When UMD calls [**D3DKMTConnectDoorbell**](../d3dkmthk/nf-d3dkmthk-d3dkmtconnectdoorbell.md), the OS calls **DxgkDdiConnectDoorbell** so that the KMD can do the following:

* Provide a CPU virtual address mapped to the physical doorbell location.
* Make the required connections between the hardware queue object, doorbell object, doorbell physical address, GPU scheduler, and so forth.

On return from this DDI, KMD should consider this physical address as reserved for this particular hardware queue. However, the OS doesn't have a uniqueness requirement for the doorbell's physical address. That is, KMD can choose to share the same physical address with multiple logical doorbells/hardware queues depending on the hardware implementation. For example, some hardware might choose to assign the same physical address to all the hardware queues of a single hardware context. It's even possible that multiple logical doorbells share the same 4KB physical page but use a unique offset within the page.

## -see-also

[**D3DKMTConnectDoorbell**](../d3dkmthk/nf-d3dkmthk-d3dkmtconnectdoorbell.md)

[**DXGKARG_CONNECTDOORBELL**](ns-d3dkmddi-dxgkarg_connectdoorbell.md)

[**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md)

[**DxgkDdiDisconnectDoorbell**](nc-d3dkmddi-dxgkddi_disconnectdoorbell.md)
