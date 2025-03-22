---
UID: NS:d3dukmdt._D3DDDI_NATIVEFENCEMAPPING
tech.root: display
title: D3DDDI_NATIVEFENCEMAPPING
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the D3DDDI_NATIVEFENCEMAPPING structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DDDI_NATIVEFENCEMAPPING
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_NATIVEFENCEMAPPING
 - D3DDDI_NATIVEFENCEMAPPING
f1_keywords:
 - _D3DDDI_NATIVEFENCEMAPPING
 - d3dukmdt/_D3DDDI_NATIVEFENCEMAPPING
 - D3DDDI_NATIVEFENCEMAPPING
 - d3dukmdt/D3DDDI_NATIVEFENCEMAPPING
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_NATIVEFENCEMAPPING
---

# D3DDDI_NATIVEFENCEMAPPING structure (d3dukmdt.h)

## -description

The **D3DDDI_NATIVEFENCEMAPPING** structure contains native GPU fence address mappings in the caller's process address space.

## -struct-fields

### -field CurrentValueCpuVa

Read-only mapping of the current value for the CPU. This value is is used by user-mode components to poll the native fence [*CurrentValue*](/windows-hardware/drivers/display/native-gpu-fence-objects).

### -field CurrentValueGpuVa

Read/write mapping of the current value for the GPU in the current process's address space. This value is used by the GPU engine to read or write to the native fence *CurrentValue* as a fence signal operation.

### -field MonitoredValueGpuVa

Read/write mapping of the monitored value for the GPU in the current process's address space. This value is used by the GPU engine to check whether a conditional CPU interrupt should be raised.

### -field Reserved[32]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**D3DDDI_NATIVEFENCEINFO**](ns-d3dukmdt-d3dddi_nativefenceinfo.md)

[**D3DKMT_CREATENATIVEFENCE**](../d3dkmthk/ns-d3dkmthk-d3dkmt_createnativefence.md)

[**D3DKMTCreateNativeFence**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatenativefence.md)
