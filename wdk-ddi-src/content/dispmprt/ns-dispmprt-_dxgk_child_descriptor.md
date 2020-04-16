---
UID: NS:dispmprt._DXGK_CHILD_DESCRIPTOR
title: _DXGK_CHILD_DESCRIPTOR (dispmprt.h)
description: The DXGK_CHILD_DESCRIPTOR structure holds identification and capability information for an individual child device of the display adapter.
old-location: display\dxgk_child_descriptor.htm
tech.root: display
ms.assetid: a814da0c-3712-4e7b-9349-a446d7b32c90
ms.date: 05/10/2018
keywords: ["_DXGK_CHILD_DESCRIPTOR structure"]
ms.keywords: "*PDXGK_CHILD_DESCRIPTOR, DXGK_CHILD_DESCRIPTOR, DXGK_CHILD_DESCRIPTOR structure [Display Devices], DmStructs_711f63dc-7ad9-49d8-b83b-5e375764a762.xml, PDXGK_CHILD_DESCRIPTOR, PDXGK_CHILD_DESCRIPTOR structure pointer [Display Devices], _DXGK_CHILD_DESCRIPTOR, display.dxgk_child_descriptor, dispmprt/DXGK_CHILD_DESCRIPTOR, dispmprt/PDXGK_CHILD_DESCRIPTOR"
f1_keywords:
 - "dispmprt/DXGK_CHILD_DESCRIPTOR"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dispmprt.h
api_name:
- DXGK_CHILD_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: DXGK_CHILD_DESCRIPTOR, *PDXGK_CHILD_DESCRIPTOR
---

# _DXGK_CHILD_DESCRIPTOR structure


## -description


The DXGK_CHILD_DESCRIPTOR structure holds identification and capability information for an individual child device of the display adapter.


## -struct-fields




### -field ChildDeviceType

A member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ne-dispmprt-_dxgk_child_device_type">DXGK_CHILD_DEVICE_TYPE</a> enumeration that indicates the type of the child device.


### -field ChildCapabilities

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_capabilities">DXGK_CHILD_CAPABILITIES</a> structure that describes the capabilities of the child device.


### -field AcpiUid

If the child device is an ACPI device, this member contains the unique ACPI identifier of the child device.


### -field ChildUid

A unique identifier, created by the display miniport driver, that identifies the child device.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a> function, implemented by the display miniport driver, fills in an array of DXGK_CHILD_DESCRIPTOR structures, one for each child device of the display adapter.

Each child device of type <b>TypeVideoOutput</b> is associated with a video present target, and the <b>ChildUid</b> member of this structure is used as the identifier for that video present target. Several functions implemented by the video present network (VidPN) manager receive a video present target identifier. For an example, see the <i>VidPnTargetId</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_capabilities">DXGK_CHILD_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ne-dispmprt-_dxgk_child_device_type">DXGK_CHILD_DEVICE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_status">DxgkDdiQueryChildStatus</a>
 

 

