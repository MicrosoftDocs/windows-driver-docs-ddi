---
UID: NC:d3dkmddi.DXGKCB_QUERYMONITORINTERFACE
title: DXGKCB_QUERYMONITORINTERFACE (d3dkmddi.h)
description: The DxgkCbQueryMonitorInterface function returns a pointer to a DXGK_MONITOR_INTERFACE structure.
old-location: display\dxgkcbquerymonitorinterface.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_QUERYMONITORINTERFACE callback function"]
ms.keywords: DXGKCB_QUERYMONITORINTERFACE, DXGKCB_QUERYMONITORINTERFACE callback, DpFunctions_6d1b7fa2-c5ab-4fd0-8a60-740c5415777c.xml, DxgkCbQueryMonitorInterface, DxgkCbQueryMonitorInterface callback function [Display Devices], d3dkmddi/DxgkCbQueryMonitorInterface, display.dxgkcbquerymonitorinterface
req.header: d3dkmddi.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_QUERYMONITORINTERFACE
 - d3dkmddi/DXGKCB_QUERYMONITORINTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_QUERYMONITORINTERFACE
product:
 - Windows
---

# DXGKCB_QUERYMONITORINTERFACE callback function

## -description

**DXGKCB_QUERYMONITORINTERFACE** obtains a pointer to a [**DXGK_MONITOR_INTERFACE**](ns-d3dkmddi-_dxgk_monitor_interface.md) structure, which contains pointers to functions that the display miniport driver can call to obtain other interfaces that provide access to monitor descriptors, modes, and frequency ranges.

## -parameters

### -param hAdapter [in]

A handle that represents a display adapter. The VidPN manager provided this handle to the display miniport driver in a call to [**DxgkDdiRecommendFunctionalVidPn**](nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md), [**DxgkDdiIsSupportedVidPn**](nc-d3dkmddi-dxgkddi_issupportedvidpn.md), [**DxgkDdiEnumVidPnCofuncModality**](nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md), or [**DxgkDdiCommitVidPn**](nc-d3dkmddi-dxgkddi_commitvidpn.md).

### -param MonitorInterfaceVersion [in]

A value from the [**DXGK_MONITOR_INTERFACE_VERSION**](ne-d3dkmddi-_dxgk_monitor_interface_version.md) enumeration that specifies the version of the monitor interface being requested.

### -param ppMonitorInterface [out]

A pointer to a pointer to the [**DXGK_MONITOR_INTERFACE**](ns-d3dkmddi-_dxgk_monitor_interface.md) structure.

## -returns

**DXGKCB_QUERYMONITORINTERFACE** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbQueryMonitorInterface** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGK_MONITOR_INTERFACE**](ns-d3dkmddi-_dxgk_monitor_interface.md)

[**DXGK_MONITOR_INTERFACE_VERSION**](ne-d3dkmddi-_dxgk_monitor_interface_version.md)
