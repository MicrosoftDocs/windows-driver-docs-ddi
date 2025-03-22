---
UID: NC:d3dkmddi.DXGKDDI_CLOSENATIVEFENCE
tech.root: display
title: DXGKDDI_CLOSENATIVEFENCE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_CLOSENATIVEFENCE function.
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
 - DXGKDDI_CLOSENATIVEFENCE
f1_keywords:
 - DXGKDDI_CLOSENATIVEFENCE
 - d3dkmddi/DXGKDDI_CLOSENATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CLOSENATIVEFENCE
---

# DXGKDDI_CLOSENATIVEFENCE function (d3dkmddi.h)

## -description

**DxgkDdiCloseNativeFence** is called by the OS to close a native GPU fence object.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pCloseNativeFence

[in/out] Pointer to a [**DXGKARG_CLOSENATIVEFENCE**](ns-d3dkmddi-dxgkarg_closenativefence.md) structure that describes the native GPU fence to open.

## -returns

**DxgkDdiCloseNativeFence** returns STATUS_SUCCESS if KMD was able to successfully open a native GPU fence object. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_CLOSENATIVEFENCE**](ns-d3dkmddi-dxgkarg_closenativefence.md)

[**DxgkDdiOpenNativeFence**](nc-d3dkmddi-dxgkddi_opennativefence.md)
