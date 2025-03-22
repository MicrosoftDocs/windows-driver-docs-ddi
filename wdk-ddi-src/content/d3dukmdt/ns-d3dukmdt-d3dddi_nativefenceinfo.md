---
UID: NS:d3dukmdt._D3DDDI_NATIVEFENCEINFO
tech.root: display
title: D3DDDI_NATIVEFENCEINFO
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the D3DDDI_NATIVEFENCEINFO structure.
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
req.typenames: D3DDDI_NATIVEFENCEINFO
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
 - _D3DDDI_NATIVEFENCEINFO
 - D3DDDI_NATIVEFENCEINFO
f1_keywords:
 - _D3DDDI_NATIVEFENCEINFO
 - d3dukmdt/_D3DDDI_NATIVEFENCEINFO
 - D3DDDI_NATIVEFENCEINFO
 - d3dukmdt/D3DDDI_NATIVEFENCEINFO
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_NATIVEFENCEINFO
---

# D3DDDI_NATIVEFENCEINFO structure (d3dukmdt.h)

## -description

**D3DDDI_NATIVEFENCEINFO** describes the attributes of a native fence synchronization object.

## -struct-fields

### -field InitialFenceValue

[in] The initial fence value.

### -field EngineAffinity

[in] Defines the physical adapters where the GPU virtual address is mapped.

### -field Type

[in] A [**D3DDDI_NATIVEFENCE_TYPE**](ne-d3dukmdt-d3dddi_nativefence_type.md) value that specifies the type of the fence.

### -field Flags

[in] A [**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md) structure that identifies the attributes of the synchronization object.

### -field NativeFenceMapping

[out] A [**D3DDDI_NATIVEFENCE_MAPPING**](ns-d3dukmdt-d3dddi_nativefencemapping.md) structure in which the process mapping information for the native fence is returned.

### -field Reserved[32]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**D3DKMT_CREATENATIVEFENCE**](../d3dkmthk/ns-d3dkmthk-d3dkmt_createnativefence.md)

[**D3DKMTCreateNativeFence**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatenativefence.md)
