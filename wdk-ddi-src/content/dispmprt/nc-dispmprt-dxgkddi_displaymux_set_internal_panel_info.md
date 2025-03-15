---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
tech.root: display
title: DXGKDDI_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_SET_INTERNAL_PANEL_INFO function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
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
 - DXGKDDI_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
f1_keywords:
 - DXGKDDI_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
 - dispmprt/DXGKDDI_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_SET_INTERNAL_PANEL_INFO
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkddiDisplayMuxSetInternalPanelInfo** function to provide the driver with information about the internal panel.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param VidPnTargetId

[in] The VidPN target that the DDI is being called for.

### -param pInternalPanelInfo

[in] Pointer to a [**DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO**](../d3dkmdt/ns-d3dkmdt-dxgk_displaymux_set_internal_panel_info.md) structure that contains information about the internal panel.

## -returns

**DxgkddiDisplayMuxSetInternalPanelInfo** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate error code.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

When an adapter is started but the mux isn't yet connected to the adapter, the driver can't communicate with the internal panel to collect information. On the first mux switch to that adapter, the OS calls **DxgkddiDisplayMuxSetInternalPanelInfo** to provide this internal panel information to the driver. The driver can subsequently report the internal panel information to the OS correctly.

**DxgkddiDisplayMuxSetInternalPanelInfo** is called only once during the first instance of a mux switch to a specific adapter after that adapter has been started, provided that the mux wasn't connected to the adapter when the adapter was started. This call is made just before [**DxgkDdiDisplayMuxPreSwitchTo**](nc-dispmprt-dxgkddi_displaymux_pre_switch_to.md) is called.

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO**](../d3dkmdt/ns-d3dkmdt-dxgk_displaymux_set_internal_panel_info.md)

[**DxgkDdiDisplayMuxPreSwitchTo**](nc-dispmprt-dxgkddi_displaymux_pre_switch_to.md)
