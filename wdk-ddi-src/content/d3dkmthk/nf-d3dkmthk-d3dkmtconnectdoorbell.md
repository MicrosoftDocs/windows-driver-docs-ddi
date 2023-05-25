---
UID: NF:d3dkmthk.D3DKMTConnectDoorbell
tech.root: display
title: D3DKMTConnectDoorbell
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the D3DKMTConnectDoorbell function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.idl: 
req.include-header: 
req.irql: 
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
 - DllExport
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTConnectDoorbell
f1_keywords:
 - D3DKMTConnectDoorbell
 - d3dkmthk/D3DKMTConnectDoorbell
dev_langs:
 - c++
helpviewer_keywords:
 - D3DKMTConnectDoorbell
---

## -description

**D3DKMTConnectDoorbell** connects (or reconnects) a [previously created doorbell object](ns-d3dkmthk-d3dkmt_create_doorbell.md) to a hardware queue.

## -parameters

### -param unnamedParam1

[in] Pointer to a [**D3DKMT_CONNECT_DOORBELL**](ns-d3dkmthk-d3dkmt_connect_doorbell.md) structure that describes the doorbell to connect.

## -returns

**D3DKMTConnectDoorbell** returns STATUS_SUCCESS when the OS successfully connects the doorbell object to the hardware queue and UMD can use this doorbell for work submission. Typically this call should not fail; however, a failure code would be from GPU lost or stop kinds of irrecoverable scenarios.

## -remarks

Each time the UMD submits new work to the queue and rings the doorbell, it must read the [**pDoorbellStatusCPUVirtualAddress**](ns-d3dkmthk-d3dkmt_create_doorbell.md) to check whether the doorbell ring succeeded. On failure, UMD must call **D3DKMTConnectDoorbell** to reconnect the doorbell and then try the submission again.

A doorbell can be disconnected for several reasons, such as the following:

* When a [doorbell is created](nf-d3dkmthk-d3dkmtcreatedoorbell.md), the OS initializes it in a "disconnected" state, and it is only connected when UMD calls **D3DKMTConnectDoorbell** for the first time.
* The doorbell was "victimized" on hardware that supports the dedicated doorbell model. That is, this hardware queue's physical doorbell was assigned to another hardware queue. This reassignment is likely because there are more hardware queues created on the GPU than physical doorbells.
* The doorbell was was disconnected as a part of suspending the hardware queue or powering down the GPU.

When UMD calls **D3DKMTConnectDoorbell** to connect the doorbell assigned to a hardware queue, the OS makes a corresponding [**DxgkDdiConnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdoorbell.md) call to KMD, so that the KMD can find a physical doorbell, assign it to this hardware queue, and make the required connections between the hardware queue, doorbell, GPU scheduler and so forth.

## -see-also

[**D3DKMT_CONNECT_DOORBELL**](ns-d3dkmthk-d3dkmt_connect_doorbell.md)

[**D3DKMTCreateDoorbell**](ns-d3dkmthk-d3dkmt_create_doorbell.md)

[**DxgkDdiConnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdoorbell.md)
