---
UID: NS:d3dukmdt._D3DDDI_CREATEHWQUEUEFLAGS
title: D3DDDI_CREATEHWQUEUEFLAGS (d3dukmdt.h)
description: Learn more about the D3DDDI_CREATEHWQUEUEFLAGS structure.
tech.root: display
ms.date: 06/17/2024
keywords: ["D3DDDI_CREATEHWQUEUEFLAGS structure"]
req.header: d3dukmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: D3DDDI_CREATEHWQUEUEFLAGS
f1_keywords:
 - _D3DDDI_CREATEHWQUEUEFLAGS
 - d3dukmdt/_D3DDDI_CREATEHWQUEUEFLAGS
 - D3DDDI_CREATEHWQUEUEFLAGS
 - d3dukmdt/D3DDDI_CREATEHWQUEUEFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_CREATEHWQUEUEFLAGS
 - D3DDDI_CREATEHWQUEUEFLAGS
---

# D3DDDI_CREATEHWQUEUEFLAGS structure

## -description

The **D3DDDI_CREATEHWQUEUEFLAGS** structure specifies flags to use when creating a hardware queue.

## -struct-fields

### -field DisableGpuTimeout

When set, indicates to the OS that the hardware queue being created is expected to submit DMA buffers that can take longer than 2 seconds to complete on the GPU, and consequently GPU timeout should be disabled.

### -field NoBroadcastSignal

When set, indicates to the OS that the hardware queue being created does not have application observable behavior, and it should not participate in D3D12 command queue fence broadcast signal operation. This flag was introduced in Windows 10, version 2004.

### -field NoBroadcastWait

When set, indicates to the OS that the hardware queue being created does not have application observable behavior, and it should not be blocked behind in D3D12 command queue fence wait operation. This flag was introduced in Windows 10, version 2004.

### -field NoKmdAccess

Reserved for system use.

### -field UserModeSubmission

When set, indicates to the OS that the hardware queue being created uses the user-mode submission model. Hardware queues created using this flag can't use the regular kernel-mode work submission path and must rely on the doorbell mechanism for work submission on the queue.

### -field NativeProgressFence

When set, indicates that the [**DXGKARG_CREATEHWQUEUE::hHwQueueProgressFence**](../d3dkmddi/ns-d3dkmddi-dxgkarg_createhwqueue.md) handle points to the driver handle of a native GPU fence object previously created using [**DxgkDdiCreateNativeFence**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createnativefence.md). For more information, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects). Available starting with Windows 11, version 24H2.

### -field TestQueue

When set, indicates that the hardware queue being created is a test queue for [kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features). Available starting with Windows 11, version 24H2.

### -field Reserved

Reserved for system use.

### -field Value

This value can be used to operate over the structure members collectively.

## -see-also

[**DxgkDdiCreateHwQueue**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createhwqueue.md)
