---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
title: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 (d3dkmddi.h)
description: Learn more about the DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback function.
ms.date: 02/03/2023
keywords: ["DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback function"]
ms.keywords: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback, DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback function [Display Devices], d3dkmddi/DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, display.dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
 - d3dkmddi/DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
---

# DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 callback function

## -description

**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3** is called to change the overlay configuration being displayed.

## -parameters

### -param hAdapter

Identifies the adapter containing the overlay hardware.

### -param pSetVidPnSourceAddressWithMultiPlaneOverlay

A pointer to a [**DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3.md) structure that describes the surfaces and display options to present.

## -returns

**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3** returns the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The routine completed successfully. |
| STATUS_INVALID_PARAMETER | In the [hardware flip queue model]/windows-hardware/drivers/display/hardware-flip-queue), the driver was unable to process a flip request. |
| STATUS_RETRY   | Returned for reasons such as the driver failed to [queue a request to the hardware](/windows-hardware/drivers/display/hardware-flip-queue) due to pending flips or the driver needs to be called at the PASSIVE_LEVEL. If the driver needs to be called at PASSIVE_LEVEL it should also set the [**DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS**](ns-d3dkmddi-_dxgk_setvidpnsourceaddress_output_flags.md).**PrePresentNeeded** flag. |

## -remarks

This function is typically called at interrupt level, but if the driver needs to perform hardware configuration that can only be performed at PASSIVE_LEVEL, the driver can request that this function be recalled at PASSIVE_LEVEL by returning STATUS_RETRY and setting the [**DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS**](ns-d3dkmddi-_dxgk_setvidpnsourceaddress_output_flags.md).**PrePresentNeeded** flag.

Even when called at PASSIVE_LEVEL, the driver should avoid spending a significant amount of time in this call because the call blocks the main GPU scheduler thread and delay could lead to present glitches. Time intensive actions should be queued as separate work items by driver and handled in background. In this scenario, any conflicts between the queued item and hardware changes demanded by future pre/post calls should be managed by the driver.

## -see-also

[**DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3.md)
