---
UID: NC:d3dkmddi.DXGKDDI_DESTROYHWQUEUE
tech.root: display
title: DXGKDDI_DESTROYHWQUEUE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_DESTROYHWQUEUE function.
prerelease: false
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
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
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
 - DXGKDDI_DESTROYHWQUEUE
f1_keywords:
 - DXGKDDI_DESTROYHWQUEUE
 - d3dkmddi/DXGKDDI_DESTROYHWQUEUE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DESTROYHWQUEUE
---

# DXGKDDI_DESTROYHWQUEUE function (d3dkmddi.h)

## -description

*Dxgkrnel* calls **DxgkDdiDestroyHwQueue** to have the kernel-mode display driver (KMD) perform the work to destroy a hardware queue.

## -parameters

### -param hHwQueue

[in] Handle to the queue to be destroyed.

## -returns

**DxgkDdiDestroyHwQueue** returns STATUS_SUCCESS if KMD was able to successfully destroy the hardware queue. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

**DxgkDdiDestroyHwQueue**'s [WDDM synchronization class is Zero level](/windows-hardware/drivers/display/threading-and-synchronization-zero-level).

## -see-also

[**DxgkDdiCreateHwQueue**](nc-d3dkmddi-dxgkddi_createhwqueue.md)
