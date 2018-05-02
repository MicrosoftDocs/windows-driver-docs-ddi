---
UID: NS:video._VIDEO_CHILD_ENUM_INFO
title: "_VIDEO_CHILD_ENUM_INFO"
author: windows-driver-content
description: Describes the child device to be enumerated by the miniport driver. All members are set by the video port driver.
old-location: display\video_child_enum_info.htm
old-project: display
ms.assetid: ce3b17e9-bcbd-46a4-b379-472abfdb4c2a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PVIDEO_CHILD_ENUM_INFO, PVIDEO_CHILD_ENUM_INFO, PVIDEO_CHILD_ENUM_INFO structure pointer [Display Devices], VIDEO_CHILD_ENUM_INFO, VIDEO_CHILD_ENUM_INFO structure [Display Devices], Video_Structs_13176852-07dc-4b7e-9e3a-c9ed9c2a3879.xml, _VIDEO_CHILD_ENUM_INFO, display.video_child_enum_info, video/PVIDEO_CHILD_ENUM_INFO, video/VIDEO_CHILD_ENUM_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_CHILD_ENUM_INFO
product:
- Windows
targetos: Windows
req.typenames: VIDEO_CHILD_ENUM_INFO, *PVIDEO_CHILD_ENUM_INFO
---

# _VIDEO_CHILD_ENUM_INFO structure


## -description


Describes the child device to be enumerated by the miniport driver. All members are set by the video port driver.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field ChildDescriptorSize

The size in bytes of the buffer to which <i>pChildDescriptor</i> points. The video port driver allocates this buffer to be large enough to accommodate a DDC2-compliant EDID structure.


### -field ChildIndex

The index of the child device for which the system is requesting information. This member is used to enumerate devices that are not enumerated by ACPI or other operating system components. If <b>ChildIndex</b> is set to zero, the driver should use the value specified in <b>ACPIHwId</b> as the ID of the device being enumerated.


### -field ACPIHwId

The identifier returned by the ACPI BIOS that represents the child device being enumerated. The miniport driver should use this member only if <b>ChildIndex</b> is zero.

The <b>ACPIHwId</b> returned by the firmware must match the value returned in <i>UId</i> by the miniport driver. The System BIOS manufacturer and the graphics IHV must synchronize these IDs.


### -field ChildHwDeviceExtension

A pointer to a device extension specific to this child device. This member is valid only if the miniport driver filled the <b>ChildHwDeviceExtensionSize</b> member of VIDEO_HW_INITIALIZATION_DATA with a value other than zero.


## -remarks



One parameter of the <i>HwVidGetVideoChildDescriptor</i> function is an instance of a VIDEO_CHILD_ENUM_INFO structure. 

The ACPI_METHOD_DISPLAY_DOD alias, defined in Dispmprt.h, represents the method used to enumerate the devices attached to the display adapter. This method is required if the integrated device controller supports switching of output devices.




## -see-also




<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570505">VIDEO_HW_INITIALIZATION_DATA</a>
 

 

