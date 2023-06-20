---
UID: NS:d3dukmdt._D3DDDI_CREATEHWQUEUEFLAGS
title: D3DDDI_CREATEHWQUEUEFLAGS (d3dukmdt.h)
description: Learn more about the D3DDDI_CREATEHWQUEUEFLAGS structure.
tech.root: display
ms.date: 05/22/2023
keywords: ["D3DDDI_CREATEHWQUEUEFLAGS structure"]
ms.keywords: D3DDDI_CREATEHWQUEUEFLAGS, D3DDDI_CREATEHWQUEUEFLAGS , D3DDDI_CREATEHWQUEUEFLAGS structure [Display Devices], _D3DDDI_CREATEHWQUEUEFLAGS, d3dukmdt/D3DDDI_CREATEHWQUEUEFLAGS, display.d3dddi_createhwqueueflags_
req.header: d3dukmdt.h
req.include-header: 
req.target-type: Windows
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

When set, indicates to the OS that the hardware queue being created will use the user-mode submission model. Hardware queues created using this flag can't use the regular kernel-mode work submission path and must rely on the doorbell mechanism for work submission on the queue.

### -field Reserved

Reserved for system use.

### -field Value

This value can be used to operate over the structure members collectively.

## -see-also

[**D3DKMT_CREATEHWQUEUE**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_createhwqueue.md)

[**PFND3DKMT_CREATEHWQUEUE**](../d3dkmthk/nc-d3dkmthk-pfnd3dkmt_createhwqueue.md)
