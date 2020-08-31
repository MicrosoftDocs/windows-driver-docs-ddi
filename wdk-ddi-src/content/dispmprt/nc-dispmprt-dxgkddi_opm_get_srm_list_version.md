---
UID: NC:dispmprt.DXGKDDI_OPM_GET_SRM_LIST_VERSION
title: DXGKDDI_OPM_GET_SRM_LIST_VERSION
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DxgkDdiOPMGetSrmListVersion function retrieves the version number of the output protection manager (OPM) system renewability message (SRM) list currently being used.
tech.root: display
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - dispmprt.h
api_name:
 - DXGKDDI_OPM_GET_SRM_LIST_VERSION
f1_keywords:
 - DXGKDDI_OPM_GET_SRM_LIST_VERSION
 - dispmprt/DXGKDDI_OPM_GET_SRM_LIST_VERSION
dev_langs:
 - c++
---

# DXGKDDI_OPM_GET_SRM_LIST_VERSION callback function


## -description

The *DxgkDdiOPMGetSrmListVersion* function retrieves the version number of the output protection manager (OPM) system renewability message (SRM) list currently being used.

## -parameters

### -param MiniportDeviceContext

Handle to a context block associated with a display adapter. Previously, the display miniport driver's [*DxgkDdiAddDevice*](..\dispmprt\nc-dispmprt-dxgkddi_add_device.md) function provided this handle to the DirectX graphics kernel subsystem.

### -param SrmListVersionSize

The size, in bytes, of the buffer that **SrmListVersionBuffer** points to.

### -param SrmListVersionBuffer

Pointer to a buffer containing the SRM list version.

## -returns

*DxgkDdiOPMGetSrmListVersion* returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in *Ntstatus.h*.

## -remarks

## -see-also

[**DXGK_OPM_INTERFACE_3**](ns-dispmprt-_dxgk_opm_interface_3.md)

[*DxgkDdiOPMSetSrmList*](nc-dispmprt-dxgkddi_opm_set_srm_list.md)

