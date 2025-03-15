---
UID: NF:d3dkmthk.D3DKMTOpenNativeFenceFromNtHandle
tech.root: display
title: D3DKMTOpenNativeFenceFromNtHandle
ms.date: 11/08/2024
targetos: Windows
description: Learn more about the D3DKMTOpenNativeFenceFromNtHandle function.
prerelease: false
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTOpenNativeFenceFromNtHandle
f1_keywords:
 - D3DKMTOpenNativeFenceFromNtHandle
 - d3dkmthk/D3DKMTOpenNativeFenceFromNtHandle
dev_langs:
 - c++
helpviewer_keywords:
 - D3DKMTOpenNativeFenceFromNtHandle
---

## -description

The D3D runtime calls ***D3DKMTOpenNativeFenceFromNTHandle** to open an existing shared native fence on a different device or process.

## -parameters

### -param unnamedParam1

[in/out] Pointer to a [**D3DKMT_OPENNATIVEFENCEFROMNTHANDLE**](ns-d3dkmthk-d3dkmt_opennativefencefromnthandle.md) structure that describes the fence object to open.

## -returns

**D3DKMTOpenNativeFenceFromNTHandle** returns STATUS_SUCCESS on successful creation. Otherwise it returns an NTSTATUS error code such as STATUS_INVALID_PARAMETER.

## -remarks

If the native fence is being opened on a different device of the same process, then [**NativeFenceMapping**](ns-d3dkmthk-d3dkmt_opennativefencefromnthandle.md) contains the same virtual addresses as the original native fence. If it is being opened on a different process, then **NativeFenceMapping** contains new VAs mapped in the new process address space.

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**D3DKMT_OPENNATIVEFENCEFROMNTHANDLE**](ns-d3dkmthk-d3dkmt_opennativefencefromnthandle.md)

[**D3DKMTCreateNativeFence**](nf-d3dkmthk-d3dkmtcreatenativefence.md)

[**D3DKMTDestroySynchronizationObject**](nf-d3dkmthk-d3dkmtdestroysynchronizationobject.md)

[**DxgkDdiOpenNativeFence**](../d3dkmddi/nc-d3dkmddi-dxgkddi_opennativefence.md)
