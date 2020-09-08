---
UID: NS:dispmprt._LINKED_DEVICE
title: _LINKED_DEVICE (dispmprt.h)
description: The LINKED_DEVICE structure holds information that describes a linked display adapter configuration.
old-location: display\linked_device.htm
tech.root: display
ms.assetid: 65289123-46b8-4a4b-985a-8087f4afd250
ms.date: 05/10/2018
keywords: ["LINKED_DEVICE structure"]
ms.keywords: "*PLINKED_DEVICE, DmStructs_3491af70-72fe-471c-b0f1-c00d6bffb242.xml, LINKED_DEVICE, LINKED_DEVICE structure [Display Devices], PLINKED_DEVICE, PLINKED_DEVICE structure pointer [Display Devices], _LINKED_DEVICE, display.linked_device, dispmprt/LINKED_DEVICE, dispmprt/PLINKED_DEVICE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: LINKED_DEVICE, *PLINKED_DEVICE
f1_keywords:
 - _LINKED_DEVICE
 - dispmprt/_LINKED_DEVICE
 - PLINKED_DEVICE
 - dispmprt/PLINKED_DEVICE
 - LINKED_DEVICE
 - dispmprt/LINKED_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - LINKED_DEVICE
---

# _LINKED_DEVICE structure


## -description

The LINKED_DEVICE structure holds information that describes a linked display adapter configuration.

## -struct-fields

### -field ChainUid

A unique identifier for this chain of display adapters.

### -field NumberOfLinksInChain

The expected number of linked adapters that the operating system should enumerate.

### -field LeadLink

A value that indicates the leading link in the chain of linked adapters. The value is <b>TRUE</b> only for the adapter that will be allowed to enumerate child adapters. Otherwise, the value is <b>FALSE</b>.

## -remarks

Prior to a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_link_device">DxgkDdiLinkDevice</a>, the display miniport driver should fill the LINKED_DEVICE structure with information about the linked adapter configuration.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_link_device">DxgkDdiLinkDevice</a>

