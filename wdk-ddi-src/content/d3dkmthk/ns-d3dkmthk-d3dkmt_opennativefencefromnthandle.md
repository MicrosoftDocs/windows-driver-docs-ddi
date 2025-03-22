---
UID: NS:d3dkmthk._D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
tech.root: display
title: D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the D3DKMT_OPENNATIVEFENCEFROMNTHANDLE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
 - D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
f1_keywords:
 - _D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
 - d3dkmthk/_D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
 - D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
 - d3dkmthk/D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_OPENNATIVEFENCEFROMNTHANDLE
---

# D3DKMT_OPENNATIVEFENCEFROMNTHANDLE structure (d3dkmthk.h)

## -description

The **D3DKMT_OPENNATIVEFENCEFROMNTHANDLE** structure is a parameter for the [**D3DKMTOpenNativeFenceFromNTHandle**](nf-d3dkmthk-d3dkmtopennativefencefromnthandle.md) function. It describes the native fence to open.

## -struct-fields

### -field hNtHandle

[in] NT handle for the shared fence object.

### -field hDevice

[in] Device handle to open this fence object on.

### -field EngineAffinity

[in] Defines the physical adapters where the GPU virtual address is mapped.

### -field Flags

[in] A [**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md) structure that identifies the attributes of the synchronization object.

### -field hSyncObject

[out] Handle to the opened fence object.

### -field NativeFenceMapping

[out] A [**D3DDDI_NATIVEFENCEMAPPING**](../d3dukmdt/ns-d3dukmdt-d3dddi_nativefencemapping.md) structure that contains process mapping information for the fence object.

### -field Reserved[32]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**D3DKMTOpenNativeFenceFromNTHandle**](nf-d3dkmthk-d3dkmtopennativefencefromnthandle.md)
