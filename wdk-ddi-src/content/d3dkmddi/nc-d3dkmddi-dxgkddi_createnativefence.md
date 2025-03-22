---
UID: NC:d3dkmddi.DXGKDDI_CREATENATIVEFENCE
tech.root: display
title: DXGKDDI_CREATENATIVEFENCE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_CREATENATIVEFENCE function.
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
req.target-min-winverclnt: Windows 11, version 24H2
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
 - DXGKDDI_CREATENATIVEFENCE
f1_keywords:
 - DXGKDDI_CREATENATIVEFENCE
 - d3dkmddi/DXGKDDI_CREATENATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CREATENATIVEFENCE
---

# DXGKDDI_CREATENATIVEFENCE function (d3dkmddi.h)

## -description

The OS calls KMD's **DxgkDdiCreateNativeFence** to create a tracking object for a native GPU fence.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pCreateNativeFence

[in/out] Pointer to a [**DXGKARG_CREATENATIVEFENCE**](ns-d3dkmddi-dxgkarg_createnativefence.md) structure that describes the native GPU fence to create.

## -returns

**DxgkDdiCreateNativeFence** returns STATUS_SUCCESS if KMD was able to successfully create a native GPU fence object. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_CREATENATIVEFENCE**](ns-d3dkmddi-dxgkarg_createnativefence.md)

[**DxgkDdiDestroyNativeFence**](nc-d3dkmddi-dxgkddi_destroynativefence.md)

[**DxgkDdiOpenNativeFence**](nc-d3dkmddi-dxgkddi_opennativefence.md)
