---
UID: NS:dispmprt._DXGK_MIPI_DSI_INTERFACE
title: DXGK_MIPI_DSI_INTERFACE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: DXGK_MIPI_DSI_INTERFACE allows the OS to request Display Serial Interface (DSI) operations to be performed on a target using a control interface to the target owned by the graphics adapter.
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
req.typenames: DXGK_MIPI_DSI_INTERFACE, *PDXGK_MIPI_DSI_INTERFACE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_MIPI_DSI_INTERFACE
 - DXGK_MIPI_DSI_INTERFACE
f1_keywords:
 - dispmprt/_DXGK_MIPI_DSI_INTERFACE
 - dispmprt//DXGK_MIPI_DSI_INTERFACE
 - DXGK_MIPI_DSI_INTERFACE
dev_langs:
 - c++
---

# DXGK_MIPI_DSI_INTERFACE structure

## -description

DXGK_MIPI_DSI_INTERFACE allows the OS to request Display Serial Interface (DSI) operations to be performed on a target using a control interface to the target owned by the graphics adapter.

## -struct-fields

### -field Size

[in] The size, in bytes, of this structure.

### -field Version

[in] The version number of the DSI interface. Version number constants are defined in *Dispmprt.h* (for example, DXGK_MIPI_DSI_INTERFACE_VERSION_1).

### -field Context

[in] Pointer to a private context block.

### -field InterfaceReference

[out] Pointer to an interface reference function that is implemented by the display miniport driver.

### -field InterfaceDereference

[out] Pointer to an interface dereference function that is implemented by the display miniport driver.

### -field DsiQueryCaps

[out] Pointer to a display miniport driver [DsiCaps](nc-dispmprt-dxgkddi_dsicaps.md) function to query capabilities for a particular target. `pArgs` is a [DXGI_DSI_CAPS](ns-dispmprt-dxgk_dsi_caps.md) structure.

### -field DsiTransmission

[out] Pointer to a display miniport driver [DsiTransmission](nc-dispmprt-dxgkddi_dsitransmission.md) function to perform a DSI transmission. `pArgs` is a [DXGI_DSI_TRANSMISSION](ns-dispmprt-dxgk_dsi_transmission.md) structure.

### -field DsiReset

[out] Pointer to a display miniport driver [DsiReset](nc-dispmprt-dxgkddi_dsireset.md) function to perform a DSI reset. `pArgs` is a [DXGI_DSI_RESET](ns-dispmprt-dxgk_dsi_reset.md) structure.

## -remarks

A kernel-mode component that needs to use the MIPI DSI Display Control interface calls the display miniport driver's [DxgkDdiQueryInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_interface) function to get its DSI-related functional interface.

## -see-also

[DXGI_DSI_CAPS](ns-dispmprt-dxgk_dsi_caps.md)

[DXGI_DSI_RESET](ns-dispmprt-dxgk_dsi_reset.md)

[DXGI_DSI_TRANSMISSION](ns-dispmprt-dxgk_dsi_transmission.md)

[DsiCaps](nc-dispmprt-dxgkddi_dsicaps.md)

[DxgkDdiQueryInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_interface)

[DsiReset](nc-dispmprt-dxgkddi_dsireset.md)

[DsiTransmission](nc-dispmprt-dxgkddi_dsitransmission.md)
