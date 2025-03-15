---
UID: NS:dispmprt._DXGK_DISPLAYMUX_INTERFACE
tech.root: display
title: DXGK_DISPLAYMUX_INTERFACE
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGK_DISPLAYMUX_INTERFACE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DISPLAYMUX_INTERFACE, *PDXGK_DISPLAYMUX_INTERFACE
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DISPLAYMUX_INTERFACE
 - PDXGK_DISPLAYMUX_INTERFACE
 - DXGK_DISPLAYMUX_INTERFACE
f1_keywords:
 - _DXGK_DISPLAYMUX_INTERFACE
 - dispmprt/_DXGK_DISPLAYMUX_INTERFACE
 - PDXGK_DISPLAYMUX_INTERFACE
 - dispmprt/PDXGK_DISPLAYMUX_INTERFACE
 - DXGK_DISPLAYMUX_INTERFACE
 - dispmprt/DXGK_DISPLAYMUX_INTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_DISPLAYMUX_INTERFACE
---

## -description

The **DXGK_DISPLAYMUX_INTERFACE** structure contains pointers to functions that are implemented by the kernel-mode display miniport driver (KMD) to support version 1 of the [automatic display switching](/windows-hardware/drivers/display/automatic-display-switch) feature. Version 1 was for the feature's pre-release; use [**DXGK_DISPLAYMUX_INTERFACE_V2**](ns-dispmprt-dxgk_displaymux_interface_2.md), which is the version released with Windows 11, version 24H2, update 2025.01 (WDDM 3.2).

## -struct-fields

### -field Size

[in] The size, in bytes, of this structure.

### -field Version

[in] The version number of the display mux interface. **Version** should be set to **DXGK_DISPLAYMUX_INTERFACE_VERSION_1** for this structure.

### -field Context

[in] A pointer to a private context block.

### -field InterfaceReference

[out] Pointer to a KMD-implemented interface reference function.

### -field InterfaceDereference

[out] Pointer to a KMD-implemented interface dereference function.

### -field DxgkDdiDisplayMuxGetDriverSupportLevel

[out] Pointer to KMD's [**DxgkDdiDisplayMuxGetDriverSupportLevel**](nc-dispmprt-dxgkddi_displaymux_get_driver_support_level.md) callback function.

### -field DxgkDdiDisplayMuxGetRuntimeStatus

[out] Pointer to KMD's [**DxgkDdiDisplayMuxGetRuntimeStatus**](nc-dispmprt-dxgkddi_displaymux_get_runtime_status.md) callback function.

### -field DxgkDdiDisplayMuxPreSwitchAway

[out] Pointer to KMD's [**DxgkDdiDisplayMuxPreSwitchAway**](nc-dispmprt-dxgkddi_displaymux_pre_switch_away.md) callback function.

### -field DxgkDdiDisplayMuxPreSwitchAwayGetPrivateData

[out] Pointer to KMD's [**DxgkDdiDisplayMuxPreSwitchAwayGetPrivateData**](nc-dispmprt-dxgkddi_displaymux_pre_switch_away_get_private_data.md) callback function.

### -field DxgkDdiDisplayMuxPreSwitchTo

[out] Pointer to KMD's [**DxgkDdiDisplayMuxPreSwitchTo**](nc-dispmprt-dxgkddi_displaymux_pre_switch_to.md) callback function.

### -field DxgkDdiDisplayMuxSwitchCanceled

[out] Pointer to KMD's [**DxgkDdiDisplayMuxSwitchCanceled**](nc-dispmprt-dxgkddi_displaymux_switch_canceled.md) callback function.

### -field DxgkDdiDisplayMuxPostSwitchAway

[out] Pointer to KMD's [**DxgkDdiDisplayMuxPostSwitchAway**](nc-dispmprt-dxgkddi_displaymux_post_switch_away.md) callback function.

### -field DxgkDdiDisplayMuxPostSwitchToPhase1

[out] Pointer to KMD's [**DxgkDdiDisplayMuxPostSwitchToPhase1**](nc-dispmprt-dxgkddi_displaymux_post_switch_to_phase1.md) callback function.

### -field DxgkDdiDisplayMuxPostSwitchToPhase2

[out] Pointer to KMD's [**DxgkDdiDisplayMuxPostSwitchToPhase2**](nc-dispmprt-dxgkddi_displaymux_post_switch_to_phase2.md) callback function.

### -field DxgkDdiDisplayMuxUpdateState

[out] Pointer to KMD's [**DxgkDdiDisplayMuxUpdateState**](nc-dispmprt-dxgkddi_displaymux_update_state.md) callback function.

### -field DxgkDdiDisplayMuxReportPresence

[out] Pointer to KMD's [**DxgkDdiDisplayMuxReportPresence**](nc-dispmprt-dxgkddi_displaymux_report_presence.md) callback function.

## -remarks

The OS queries for KMD's **DXGK_DISPLAYMUX_INTERFACE** at driver start. It does so by calling KMD's [**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md) function with [**QueryInterface->InterfaceType**](../video/ns-video-_query_interface.md) set to GUID_WDDM_INTERFACE_DISPLAYMUX. If the KMD supports this interface, it returns a **DXGK_DISPLAYMUX_INTERFACE** structure with pointers to its automatic display switch callbacks.

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DXGK_DISPLAYMUX_INTERFACE_V2**](ns-dispmprt-dxgk_displaymux_interface_2.md)

[**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md)

[**QUERY_INTERFACE**](../video/ns-video-_query_interface.md)
