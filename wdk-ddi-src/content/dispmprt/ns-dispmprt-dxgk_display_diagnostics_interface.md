---
UID: NS:dispmprt._DXGK_DISPLAY_DIAGNOSTICS_INTERFACE
title: DXGK_DISPLAY_DIAGNOSTICS_INTERFACE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: A kernel-mode component that needs to use the display diagnostics interface calls the display miniport driver's DxgkDdiQueryInterface function.
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DISPLAY_DIAGNOSTICS_INTERFACE, *PDXGK_DISPLAY_DIAGNOSTICS_INTERFACE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DISPLAY_DIAGNOSTICS_INTERFACE
 - DXGK_DISPLAY_DIAGNOSTICS_INTERFACE
f1_keywords:
 - dispmprt/_DXGK_DISPLAY_DIAGNOSTICS_INTERFACE
 - dispmprt/DXGK_DISPLAY_DIAGNOSTICS_INTERFACE
dev_langs:
 - c++
---

# DXGK_DISPLAY_DIAGNOSTICS_INTERFACE structure

## -description

A kernel-mode component that needs to use the display diagnostics interface calls the display miniport driver's **DxgkDdiQueryInterface** function.

## -struct-fields

### -field Size

[in] Size, in bytes, of this structure.

### -field Version

[in] Version number of the display diagnostics interface. Version number constants are defined in *dispmprt.h* (for example, DXGK_DISPLAY_DIAGNOSTICS_INTERFACE_VERSION_1).

### -field Context

[out] Pointer to a private context block provided by the display miniport driver. The operating system will provide this *Context* back to the driver in interface DDI calls. The driver should ensure that this context is adapter-specific and not driver-global because the operating system stores the interface information per adapter.

### -field InterfaceReference

[out] Pointer to the display miniport driver's [interface reference function](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference).

### -field InterfaceDereference

[out] Pointer the display miniport driver's [interface dereference function](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference).

### -field DxgkDdiGetDisplayStateNonIntrusive

[out] Pointer to the display miniport driver's [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md) function.

### -field DxgkDdiGetDisplayStateIntrusive

[out] Pointer to the display miniport driver's [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md) function.

## -remarks

The operating system will query the display diagnostics interface for each graphics adapter when they are started.

## -see-also

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)

[**PINTERFACE_DEREFERENCE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference)

[**PINTERFACE_REFERENCE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference)
