---
UID: NS:video._VIDEO_PORT_I2C_INTERFACE
title: "_VIDEO_PORT_I2C_INTERFACE"
author: windows-driver-content
description: The VIDEO_PORT_I2C_INTERFACE structure describes the I2C service routines provided by the video port driver.
old-location: display\video_port_i2c_interface.htm
old-project: display
ms.assetid: fcc2679c-9a73-4bd0-ad2d-e7b48df9c7f7
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PVIDEO_PORT_I2C_INTERFACE, PVIDEO_PORT_I2C_INTERFACE, PVIDEO_PORT_I2C_INTERFACE structure pointer [Display Devices], VIDEO_PORT_I2C_INTERFACE, VIDEO_PORT_I2C_INTERFACE structure [Display Devices], Video_Structs_2b152aec-acc0-4602-80de-cfdf9c0632a4.xml, _VIDEO_PORT_I2C_INTERFACE, display.video_port_i2c_interface, video/PVIDEO_PORT_I2C_INTERFACE, video/VIDEO_PORT_I2C_INTERFACE"
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
-	VIDEO_PORT_I2C_INTERFACE
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_I2C_INTERFACE, *PVIDEO_PORT_I2C_INTERFACE
---

# _VIDEO_PORT_I2C_INTERFACE structure


## -description


The VIDEO_PORT_I2C_INTERFACE structure describes the <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> service routines provided by the video port driver. 


## -struct-fields




### -field Size

Specifies the size in bytes of this structure.


### -field Version

Specifies the version of the interface to be returned by the miniport driver. The current interface version is defined in <i>video.h</i>, and has the form VIDEO_PORT_I2C_INTERFACE_<i>N</i>.


### -field Context

Pointer to a miniport driver-defined context for the interface.


### -field InterfaceReference

Pointer to the video port driver-implemented reference routine for this interface.


### -field InterfaceDereference

Pointer to the video port driver-implemented dereference routine for this interface.


### -field I2CStart

Pointer to the video port driver's <a href="https://msdn.microsoft.com/90f0a38d-f50e-4da0-b98f-2f3068f03b2e">I2CStart</a> routine.


### -field I2CStop

Pointer to the video port driver's <a href="https://msdn.microsoft.com/535e1603-08e3-4ad1-b4e5-f0368b7d3e71">I2CStop</a> routine.


### -field I2CWrite

Pointer to the video port driver's <a href="https://msdn.microsoft.com/5aaebf38-bc09-4fb5-969e-7b456773d5ac">I2CWrite</a> routine.


### -field I2CRead

Pointer to the video port driver's <a href="https://msdn.microsoft.com/1418ec29-be67-46af-b6db-0b534ecafb37">I2CRead</a> routine.


## -remarks



PnP video miniport drivers that can use I²C should fill in the <b>Size</b> and <b>Version</b> members of this structure, and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>, which initializes the remaining members of this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>
 

 

