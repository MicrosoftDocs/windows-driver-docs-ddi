---
UID: NS:dispmprt._DXGK_CHILD_DESCRIPTOR
title: "_DXGK_CHILD_DESCRIPTOR"
author: windows-driver-content
description: The DXGK_CHILD_DESCRIPTOR structure holds identification and capability information for an individual child device of the display adapter.
old-location: display\dxgk_child_descriptor.htm
old-project: display
ms.assetid: a814da0c-3712-4e7b-9349-a446d7b32c90
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PDXGK_CHILD_DESCRIPTOR, DXGK_CHILD_DESCRIPTOR, DXGK_CHILD_DESCRIPTOR structure [Display Devices], DmStructs_711f63dc-7ad9-49d8-b83b-5e375764a762.xml, PDXGK_CHILD_DESCRIPTOR, PDXGK_CHILD_DESCRIPTOR structure pointer [Display Devices], _DXGK_CHILD_DESCRIPTOR, display.dxgk_child_descriptor, dispmprt/DXGK_CHILD_DESCRIPTOR, dispmprt/PDXGK_CHILD_DESCRIPTOR"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGK_CHILD_DESCRIPTOR
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

A member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561008">DXGK_CHILD_DEVICE_TYPE</a> enumeration that indicates the type of the child device.


### -field ChildCapabilities

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560995">DXGK_CHILD_CAPABILITIES</a> structure that describes the capabilities of the child device.


### -field AcpiUid

If the child device is an ACPI device, this member contains the unique ACPI identifier of the child device.


### -field ChildUid

A unique identifier, created by the display miniport driver, that identifies the child device.


## -remarks



The <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a> function, implemented by the display miniport driver, fills in an array of DXGK_CHILD_DESCRIPTOR structures, one for each child device of the display adapter.

Each child device of type <b>TypeVideoOutput</b> is associated with a video present target, and the <b>ChildUid</b> member of this structure is used as the identifier for that video present target. Several functions implemented by the video present network (VidPN) manager receive a video present target identifier. For an example, see the <i>VidPnTargetId</i> parameter of the <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560995">DXGK_CHILD_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561008">DXGK_CHILD_DEVICE_TYPE</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>



<a href="https://msdn.microsoft.com/478e0c52-4324-4062-8e1e-381808b0f481">DxgkDdiQueryChildStatus</a>
 

 

