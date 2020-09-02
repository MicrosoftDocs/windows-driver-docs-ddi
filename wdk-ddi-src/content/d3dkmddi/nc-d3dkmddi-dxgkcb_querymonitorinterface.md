---
UID: NC:d3dkmddi.DXGKCB_QUERYMONITORINTERFACE
title: DXGKCB_QUERYMONITORINTERFACE (d3dkmddi.h)
description: The DxgkCbQueryMonitorInterface function returns a pointer to a DXGK_MONITOR_INTERFACE structure.
old-location: display\dxgkcbquerymonitorinterface.htm
ms.assetid: 0c23e72d-3eb9-4511-a386-1dcc2f4910b7
ms.date: 05/10/2018
keywords: ["DXGKCB_QUERYMONITORINTERFACE callback function"]
ms.keywords: DXGKCB_QUERYMONITORINTERFACE, DXGKCB_QUERYMONITORINTERFACE callback, DpFunctions_6d1b7fa2-c5ab-4fd0-8a60-740c5415777c.xml, DxgkCbQueryMonitorInterface, DxgkCbQueryMonitorInterface callback function [Display Devices], d3dkmddi/DxgkCbQueryMonitorInterface, display.dxgkcbquerymonitorinterface
req.header: d3dkmddi.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
 - DxgkCbQueryMonitorInterface
product:
 - Windows
---

# DXGKCB_QUERYMONITORINTERFACE callback function


## -description

The <b>DxgkCbQueryMonitorInterface</b> function returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface">DXGK_MONITOR_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to obtain other interfaces that provide access to monitor descriptors, modes, and frequency ranges.

## -parameters

### -param hAdapter

[in] A handle that represents a display adapter. The VidPN manager provided this handle to the display miniport driver in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a>.

### -param MonitorInterfaceVersion

[in] A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_monitor_interface_version">DXGK_MONITOR_INTERFACE_VERSION</a> enumeration that specifies the version of the monitor interface being requested.

### -param ppMonitorInterface

[out] A pointer to a variable that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface">DXGK_MONITOR_INTERFACE</a> structure.

## -returns

<b>DxgkCbQueryMonitorInterface</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.</i>h.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Monitor Interface</a>

