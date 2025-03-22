---
UID: NC:d3dkmddi.DXGKDDI_OPENNATIVEFENCE
tech.root: display
title: DXGKDDI_OPENNATIVEFENCE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_OPENNATIVEFENCE function.
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
 - DXGKDDI_OPENNATIVEFENCE
f1_keywords:
 - DXGKDDI_OPENNATIVEFENCE
 - d3dkmddi/DXGKDDI_OPENNATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_OPENNATIVEFENCE
---

# DXGKDDI_OPENNATIVEFENCE function (d3dkmddi.h)

## -description

**DxgkDdiOpenNativeFence** is called by the OS to open a native GPU fence object.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pOpenNativeFence

[in/out] Pointer to a [**DXGKARG_OPENNATIVEFENCE**](ns-d3dkmddi-dxgkarg_opennativefence.md) structure that describes the native GPU fence to open.

## -returns

**DxgkDdiOpenNativeFence** returns STATUS_SUCCESS if KMD was able to successfully open a native GPU fence object. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

 **DxgkDdiOpenNativeFence** is always preceded by a call to [**DxgkDdiCreateNativeFence**](nc-d3dkmddi-dxgkddi_createnativefence.md).

If a second process opens the shared native fence object using [**D3DKMT_OPENNATIVEFENCEFROMNTHANDLE**](../d3dkmthk/nf-d3dkmthk-d3dkmtopennativefencefromnthandle.md), *Dxgkrnl* does the following:

* Locates the **hGlobalNativeFence**.
* Creates a new CPU virtual address (VA) and GPU VA mapping for that existing object in the second process's address space.

*Dxgkrnl* passes this payload to the KMD by calling **DxgkDdiOpenNativeFence** along with a new [**hLocalNativeFence**](ns-d3dkmddi-dxgkarg_opennativefence.md) handle.

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_OPENNATIVEFENCE**](ns-d3dkmddi-dxgkarg_opennativefence.md)

[**DxgkDdiCloseNativeFence**](nc-d3dkmddi-dxgkddi_closenativefence.md)

[**DxgkDdiCreateNativeFence**](nc-d3dkmddi-dxgkddi_createnativefence.md)
