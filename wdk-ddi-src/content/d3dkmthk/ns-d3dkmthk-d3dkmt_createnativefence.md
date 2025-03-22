---
UID: NS:d3dkmthk._D3DKMT_CREATENATIVEFENCE
tech.root: display
title: D3DKMT_CREATENATIVEFENCE
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the D3DKMT_CREATENATIVEFENCE structure.
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
req.typenames: D3DKMT_CREATENATIVEFENCE
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
 - _D3DKMT_CREATENATIVEFENCE
 - D3DKMT_CREATENATIVEFENCE
f1_keywords:
 - _D3DKMT_CREATENATIVEFENCE
 - d3dkmthk/_D3DKMT_CREATENATIVEFENCE
 - D3DKMT_CREATENATIVEFENCE
 - d3dkmthk/D3DKMT_CREATENATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_CREATENATIVEFENCE
---

# D3DKMT_CREATENATIVEFENCE structure (d3dkmthk.h)

## -description

The **D3DKMT_CREATENATIVEFENCE** structure is a parameter for the [**D3DKMTCreateNativeFence**](nf-d3dkmthk-d3dkmtcreatenativefence.md) function. It describes the fence object to create.

## -struct-fields

### -field hDevice

[in] A handle to the device that the fence object is created on.

### -field hSyncObject

[out] A handle to the sync object on this process.

### -field PrivateDriverData[D3DDDI_NATIVE_FENCE_PDD_SIZE]

[in/out] Private driver data to pass to KMD's [**DxgkDdiCreateNativeFence**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createnativefence.md) function and copy back to UMD.

### -field Info

[in/out] A [**D3DDDI_NATIVEFENCEINFO**](../d3dukmdt/ns-d3dukmdt-d3dddi_nativefenceinfo.md) structure that describes the attributes of the synchronization object.

### -field Flags

[in] A [**D3DKMT_CREATENATIVEFENCE_FLAGS**](ns-d3dkmthk-d3dkmt_createnativefence_flags.md) structure that describes the flags for the fence object.

### -field Reserved[28]

Reserved for system use.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**D3DKMTCreateNativeFence**](nf-d3dkmthk-d3dkmtcreatenativefence.md)

[**DxgkDdiCreateNativeFence**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createnativefence.md)
