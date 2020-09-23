---
UID: NC:d3dkmddi.DXGKDDI_QUERYVIDPNHWCAPABILITY
title: DXGKDDI_QUERYVIDPNHWCAPABILITY (d3dkmddi.h)
description: The DxgkDdiQueryVidPnHWCapability function requests that the display miniport driver report the capabilities of the hardware on a functional VidPn path.
old-location: display\dxgkddiqueryvidpnhwcapability.htm
ms.assetid: 41af9528-4497-41aa-a65d-70352aa85f8c
ms.date: 05/10/2018
keywords: ["DXGKDDI_QUERYVIDPNHWCAPABILITY callback function"]
ms.keywords: DXGKDDI_QUERYVIDPNHWCAPABILITY, DXGKDDI_QUERYVIDPNHWCAPABILITY callback, DmFunctions_2e9dffd4-d8af-49f9-86d4-7a67e18df2dc.xml, DxgkDdiQueryVidPnHWCapability, DxgkDdiQueryVidPnHWCapability callback function [Display Devices], d3dkmddi/DxgkDdiQueryVidPnHWCapability, display.dxgkddiqueryvidpnhwcapability
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_QUERYVIDPNHWCAPABILITY
 - d3dkmddi/DXGKDDI_QUERYVIDPNHWCAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiQueryVidPnHWCapability
product:
 - Windows
---

# DXGKDDI_QUERYVIDPNHWCAPABILITY callback function


## -description

The <i>DxgkDdiQueryVidPnHWCapability</i> function requests that the display miniport driver report the capabilities of the hardware on a functional VidPn path.

## -parameters

### -param i_hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param io_pVidPnHWCaps

[in/out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryvidpnhwcapability">DXGKARG_QUERYVIDPNHWCAPABILITY</a> structure that describes the hardware capabilities of a functional VidPN.

## -returns

<i>DxgkDdiQueryVidPnHwCapability </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks

For more information on how to process this function, see <a href="/windows-hardware/drivers/display/querying-vidpnhardware-capabilities">Querying VidPN Hardware Capabilities</a>.

<i>DxgkDdiQueryInterface</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryvidpnhwcapability">DXGKARG_QUERYVIDPNHWCAPABILITY</a>