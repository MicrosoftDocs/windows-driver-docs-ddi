---
UID: NS:d3dkmddi._DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
title: DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS (d3dkmddi.h)
description: Learn more about the DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS structure.
old-location: display\dxgk_setvidpnsourceaddress_output_flags.htm
ms.date: 02/03/2023
keywords: ["DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS structure"]
ms.keywords: DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS, DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS structure [Display Devices], _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS, d3dkmddi/DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS, display.dxgk_setvidpnsourceaddress_output_flags
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
req.typenames: DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
f1_keywords:
 - _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
 - d3dkmddi/_DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
 - DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
 - d3dkmddi/DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
 - DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
---

# DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS structure

## -description

The **DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS** structure contains the flags used to set the VidPN source address.

## -struct-fields

### -field PrePresentNeeded

Indicates that the driver must be called again at the PASSIVE_LEVEL to perform the requested operation.

### -field HwFlipQueueDrainNeeded

Indicates that the OS should attempt to submit the flip request again after all pending flips on planes affected by this flip are finished and once the target time is reached. See [Hardware flip queue](/windows-hardware/drivers/display/hardware-flip-queue) for more information.

### -field HwFlipQueueDrainAllPlanes

Indicates that the display hardware may require completion of pending flips on all planes, not just the ones referenced by the incoming flip request. In this case, the driver should set both the **HwFlipQueueDrainNeeded** and **HwFlipQueueDrainAllPlanes**. See [Hardware flip queue](/windows-hardware/drivers/display/hardware-flip-queue) for more information.

### -field HwFlipQueueDrainAllSources

Indicates that the the display hardware may require completion of pending flips on all VidPn sources in order to reallocate internal resources. In this case, the driver should set both the **HwFlipQueueDrainNeeded** and **HwFlipQueueDrainAllSources** flags. See [Hardware flip queue](/windows-hardware/drivers/display/hardware-flip-queue) for more information.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

An alternative way to access the bits.

## -see-also

[**DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3.md)

[**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md)
