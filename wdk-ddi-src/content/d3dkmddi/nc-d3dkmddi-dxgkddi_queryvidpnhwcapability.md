---
UID: NC:d3dkmddi.DXGKDDI_QUERYVIDPNHWCAPABILITY
title: DXGKDDI_QUERYVIDPNHWCAPABILITY (d3dkmddi.h)
description: Learn more about the DxgkDdiQueryVidPnHWCapability function.
ms.date: 06/09/2023
keywords: ["DXGKDDI_QUERYVIDPNHWCAPABILITY callback function"]
ms.keywords: DXGKDDI_QUERYVIDPNHWCAPABILITY, DXGKDDI_QUERYVIDPNHWCAPABILITY callback, DmFunctions_2e9dffd4-d8af-49f9-86d4-7a67e18df2dc.xml, DxgkDdiQueryVidPnHWCapability, DxgkDdiQueryVidPnHWCapability callback function [Display Devices], d3dkmddi/DxgkDdiQueryVidPnHWCapability, display.dxgkddiqueryvidpnhwcapability
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 7
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
 - DXGKDDI_QUERYVIDPNHWCAPABILITY
product:
 - Windows
---

# DXGKDDI_QUERYVIDPNHWCAPABILITY callback function

## -description

The **DxgkDdiQueryVidPnHWCapability** function requests that the display miniport driver report the capabilities of the hardware on a functional VidPn path.

## -parameters

### -param i_hAdapter [in]

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param io_pVidPnHWCaps [in/out]

A pointer to a [**DXGKARG_QUERYVIDPNHWCAPABILITY**](ns-d3dkmddi-_dxgkarg_queryvidpnhwcapability.md) structure that describes the hardware capabilities of a functional VidPN.

## -returns

**DxgkDdiQueryVidPnHwCapability** returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

For more information on how to process this function, see [Querying VidPN Hardware Capabilities](/windows-hardware/drivers/display/querying-vidpnhardware-capabilities).

**DxgkDdiQueryInterface** should be made pageable.

## -see-also

[**DXGKARG_QUERYVIDPNHWCAPABILITY**](ns-d3dkmddi-_dxgkarg_queryvidpnhwcapability.md)
