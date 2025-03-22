---
UID: NC:d3dkmddi.DXGKDDI_DESTROYNATIVEFENCE
tech.root: display
title: DXGKDDI_DESTROYNATIVEFENCE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_DESTROYNATIVEFENCE function.
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
 - DXGKDDI_DESTROYNATIVEFENCE
f1_keywords:
 - DXGKDDI_DESTROYNATIVEFENCE
 - d3dkmddi/DXGKDDI_DESTROYNATIVEFENCE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DESTROYNATIVEFENCE
---

# DXGKDDI_DESTROYNATIVEFENCE function (d3dkmddi.h)

## -description

The OS calls KMD's **DxgkDdiDestroyNativeFence** to destroy a tracking object for a native GPU fence.

## -parameters

### -param pDestroyNativeFence

[in/out] Pointer to a [**DXGKARG_DESTROYNATIVEFENCE**](ns-d3dkmddi-dxgkarg_destroynativefence.md) structure that describes the native GPU fence object to destroy.

## -returns

**DxgkDdiDestroyNativeFence** returns STATUS_SUCCESS if KMD was able to successfully destroy the native GPU fence object. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

The OS calls **DxgkDdiDestroyNativeFence** to instruct the KMD to destroy the driver tracking object for a given native GPU fence. After the call returns, the OS will deallocate storage for **CurrentValue** and **MonitoredValue**.

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_DESTROYNATIVEFENCE**](ns-d3dkmddi-dxgkarg_destroynativefence.md)

[**DxgkDdiCreateNativeFence**](nc-d3dkmddi-dxgkddi_createnativefence.md)
