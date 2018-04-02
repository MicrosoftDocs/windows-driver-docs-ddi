---
UID: NS:dispmprt._DXGK_GENERIC_DESCRIPTOR
title: "_DXGK_GENERIC_DESCRIPTOR"
author: windows-driver-content
description: The DXGK_GENERIC_DESCRIPTOR structure contains descriptive information about a child device of the display adapter.
old-location: display\dxgk_generic_descriptor.htm
old-project: display
ms.assetid: 181df1a6-044d-406d-bc6d-1b35b3d744fc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_GENERIC_DESCRIPTOR, DXGK_GENERIC_DESCRIPTOR, DXGK_GENERIC_DESCRIPTOR structure [Display Devices], DmStructs_f77c03e6-d887-43ba-9499-ce1740cb6c9e.xml, PDXGK_GENERIC_DESCRIPTOR, PDXGK_GENERIC_DESCRIPTOR structure pointer [Display Devices], _DXGK_GENERIC_DESCRIPTOR, display.dxgk_generic_descriptor, dispmprt/DXGK_GENERIC_DESCRIPTOR, dispmprt/PDXGK_GENERIC_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_GENERIC_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DXGK_GENERIC_DESCRIPTOR, *PDXGK_GENERIC_DESCRIPTOR
---

# _DXGK_GENERIC_DESCRIPTOR structure


## -description


The DXGK_GENERIC_DESCRIPTOR structure contains descriptive information about a child device of the display adapter.


## -struct-fields




### -field HardwareId

A single wide-character string, terminated by two wide NULL characters, that holds the hardware ID of the child device.


### -field InstanceId

A single wide-character string, terminated by two wide NULL characters, that holds the instance ID of the child device.


### -field CompatibleId

A sequence of wide-character strings, each of which is terminated by a single wide NULL character. The last string in the sequence is terminated by two wide NULL characters.


### -field DeviceText

A single wide-character string, terminated by two wide NULL characters, that holds the device text of the child device.


## -remarks



The display adapter has two types of child devices: <b>TypeVideoOutput</b> and <b>TypeOther</b>. For child devices of type <b>TypeOther</b>, the display port driver passes a DXGK_GENERIC_DESCRIPTOR structure to the display miniport driver's <a href="https://msdn.microsoft.com/0dfcc012-9fff-40b6-b71f-da2ca229896c">DxgkDdiQueryDeviceDescriptor</a> function. <i>DxgkDdiQueryDeviceDescriptor</i> must fill in the members of the structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561050">DXGK_DEVICE_DESCRIPTOR</a>
 

 

