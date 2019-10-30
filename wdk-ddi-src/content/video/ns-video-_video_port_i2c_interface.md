---
UID: NS:video._VIDEO_PORT_I2C_INTERFACE
title: _VIDEO_PORT_I2C_INTERFACE (video.h)
description: The VIDEO_PORT_I2C_INTERFACE structure describes the I2C service routines provided by the video port driver.
old-location: display\video_port_i2c_interface.htm
tech.root: display
ms.assetid: fcc2679c-9a73-4bd0-ad2d-e7b48df9c7f7
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_PORT_I2C_INTERFACE, PVIDEO_PORT_I2C_INTERFACE, PVIDEO_PORT_I2C_INTERFACE structure pointer [Display Devices], VIDEO_PORT_I2C_INTERFACE, VIDEO_PORT_I2C_INTERFACE structure [Display Devices], Video_Structs_2b152aec-acc0-4602-80de-cfdf9c0632a4.xml, _VIDEO_PORT_I2C_INTERFACE, display.video_port_i2c_interface, video/PVIDEO_PORT_I2C_INTERFACE, video/VIDEO_PORT_I2C_INTERFACE"
ms.topic: struct
f1_keywords:
 - "video/VIDEO_PORT_I2C_INTERFACE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- video.h
api_name:
- VIDEO_PORT_I2C_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_I2C_INTERFACE, *PVIDEO_PORT_I2C_INTERFACE
---

# _VIDEO_PORT_I2C_INTERFACE structure


## -description


The VIDEO_PORT_I2C_INTERFACE structure describes the <a href="https://docs.microsoft.com/windows-hardware/drivers/">I2C</a> service routines provided by the video port driver. 


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

Pointer to the video port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pi2c_start">I2CStart</a> routine.


### -field I2CStop

Pointer to the video port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pi2c_stop">I2CStop</a> routine.


### -field I2CWrite

Pointer to the video port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pi2c_write">I2CWrite</a> routine.


### -field I2CRead

Pointer to the video port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pi2c_read">I2CRead</a> routine.


## -remarks



PnP video miniport drivers that can use I²C should fill in the <b>Size</b> and <b>Version</b> members of this structure, and then call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>, which initializes the remaining members of this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>
 

 

