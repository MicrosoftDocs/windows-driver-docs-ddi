---
UID: NE:dispmprt._DXGK_CHILD_DEVICE_TYPE
title: "_DXGK_CHILD_DEVICE_TYPE"
author: windows-driver-content
description: The DXGK_CHILD_DEVICE_TYPE enumeration is used to indicate the type of a child device of the display adapter.
old-location: display\dxgk_child_device_type.htm
old-project: display
ms.assetid: b16ba776-a6b2-46d0-9b6f-18ea17cf4fce
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_CHILD_DEVICE_TYPE, DXGK_CHILD_DEVICE_TYPE, TypeIntegratedDisplay, dispmprt/TypeIntegratedDisplay, dispmprt/TypeUninitialized, TypeOther, PDXGK_CHILD_DEVICE_TYPE, *PDXGK_CHILD_DEVICE_TYPE, dispmprt/PDXGK_CHILD_DEVICE_TYPE, DXGK_CHILD_DEVICE_TYPE enumeration [Display Devices], TypeVideoOutput, PDXGK_CHILD_DEVICE_TYPE enumeration pointer [Display Devices], display.dxgk_child_device_type, TypeUninitialized, DmEnums_afd3654c-ffb4-49d6-ba59-235148e59d2c.xml, dispmprt/TypeVideoOutput, dispmprt/TypeOther, dispmprt/DXGK_CHILD_DEVICE_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DXGK_CHILD_DEVICE_TYPE
product: Windows
targetos: Windows
req.typenames: DXGK_CHILD_DEVICE_TYPE, *PDXGK_CHILD_DEVICE_TYPE
---

# _DXGK_CHILD_DEVICE_TYPE enumeration


## -description


The DXGK_CHILD_DEVICE_TYPE enumeration is used to indicate the type of a child device of the display adapter.


## -syntax


````
typedef enum _DXGK_CHILD_DEVICE_TYPE { 
  TypeUninitialized,
  TypeVideoOutput,
  TypeOther,
  TypeIntegratedDisplay
} DXGK_CHILD_DEVICE_TYPE, *PDXGK_CHILD_DEVICE_TYPE;
````


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



The <b>ChildDeviceType</b> member of a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structure is a DXGK_CHILD_DEVICE_TYPE value.

For more information about child devices of display adapters, see <a href="https://msdn.microsoft.com/9fd20e1a-db98-4571-8fc4-6d33fd0e2f16">Child Devices of the Display Adapter</a> and <a href="https://msdn.microsoft.com/3bec2117-aef4-41fc-b88a-0081c7c9fe3d">Enumerating Child Devices of a Display Adapter</a>.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



<a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CHILD_DEVICE_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

