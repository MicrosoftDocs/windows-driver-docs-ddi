---
UID: NE:dispmprt._DXGK_CHILD_DEVICE_TYPE
title: _DXGK_CHILD_DEVICE_TYPE (dispmprt.h)
description: The DXGK_CHILD_DEVICE_TYPE enumeration is used to indicate the type of a child device of the display adapter.
old-location: display\dxgk_child_device_type.htm
tech.root: display
ms.assetid: b16ba776-a6b2-46d0-9b6f-18ea17cf4fce
ms.date: 05/10/2018
keywords: ["_DXGK_CHILD_DEVICE_TYPE enumeration"]
ms.keywords: "*PDXGK_CHILD_DEVICE_TYPE, DXGK_CHILD_DEVICE_TYPE, DXGK_CHILD_DEVICE_TYPE enumeration [Display Devices], DmEnums_afd3654c-ffb4-49d6-ba59-235148e59d2c.xml, PDXGK_CHILD_DEVICE_TYPE, PDXGK_CHILD_DEVICE_TYPE enumeration pointer [Display Devices], TypeIntegratedDisplay, TypeOther, TypeUninitialized, TypeVideoOutput, _DXGK_CHILD_DEVICE_TYPE, display.dxgk_child_device_type, dispmprt/DXGK_CHILD_DEVICE_TYPE, dispmprt/PDXGK_CHILD_DEVICE_TYPE, dispmprt/TypeIntegratedDisplay, dispmprt/TypeOther, dispmprt/TypeUninitialized, dispmprt/TypeVideoOutput"
f1_keywords:
 - "dispmprt/DXGK_CHILD_DEVICE_TYPE"
 - "DXGK_CHILD_DEVICE_TYPE"
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
- dispmprt.h
api_name:
- DXGK_CHILD_DEVICE_TYPE
product:
- Windows
targetos: Windows
req.typenames: DXGK_CHILD_DEVICE_TYPE, *PDXGK_CHILD_DEVICE_TYPE
---

# _DXGK_CHILD_DEVICE_TYPE enumeration


## -description


The DXGK_CHILD_DEVICE_TYPE enumeration is used to indicate the type of a child device of the display adapter.


## -enum-fields




### -field TypeUninitialized

Indicates that a variable of type DXGK_CHILD_DEVICE_TYPE has not yet been assigned a meaningful value.


### -field TypeVideoOutput

Indicates that the child device is a video output. A video output is the circuitry on the display adapter that supplies a video signal to an external or integrated monitor (or other display device). Note that monitors, integrated LCD panels, and other devices that actually display an image are not considered child devices of the display adapter. 


### -field TypeOther

Indicates that the child device is not a video output. TV tuners, crossbar switches, and MPEG2 codecs are examples of child devices that are not video outputs.


### -field TypeIntegratedDisplay

Type indicating that this target is permanently connected to an integrated display.


## -remarks



The <b>ChildDeviceType</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structure is a DXGK_CHILD_DEVICE_TYPE value.

For more information about child devices of display adapters, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/child-devices-of-the-display-adapter">Child Devices of the Display Adapter</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/display/enumerating-child-devices-of-a-display-adapter">Enumerating Child Devices of a Display Adapter</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>
 

 

