---
UID: NC:d3dkmddi.DXGKDDI_DESTROYMEMORYBASIS
tech.root: display
title: DXGKDDI_DESTROYMEMORYBASIS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_DESTROYMEMORYBASIS function.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
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
 - DXGKDDI_DESTROYMEMORYBASIS
f1_keywords:
 - DXGKDDI_DESTROYMEMORYBASIS
 - d3dkmddi/DXGKDDI_DESTROYMEMORYBASIS
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DESTROYMEMORYBASIS
---

# DXGKDDI_DESTROYMEMORYBASIS function (d3dkmddi.h)

## -description

KMD's **DxgkDdiDestroyMemoryBasis** function destroys a memory basis that was created by a previous call to [**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md).

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgiDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param hMemoryBasis

Handle to the memory basis to destroy. This handle was previously created by a call to [**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md).

## -returns

**DxgkDdiDestroyMemoryBasis** returns STATUS_SUCCESS if the memory basis was successfully destroyed. Otherwise, it returns an NTSTATUS error code. See Remarks.

## -remarks

*Dxgkrnl* interprets any returned NTSTATUS that isn't STATUS_SUCCESS as a catastrophic error notification return. There should be no correct-functioning path to return anything but success from this function, as it should be an  assumed invariant that the supplied handle is one that was created and has not yet been destroyed. If KMD detects bad input, a returned error code lets *Dxgkrnl* assign the invariant failure to the OS kernel instead of a driver crash.

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md)
