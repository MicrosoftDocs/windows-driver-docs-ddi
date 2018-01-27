---
UID: NC:video.PI2C_WRITE
title: PI2C_WRITE
author: windows-driver-content
description: The I2CWrite function writes data over the I2C channel.
old-location: display\i2cwrite.htm
old-project: display
ms.assetid: 5aaebf38-bc09-4fb5-969e-7b456773d5ac
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.i2cwrite, I2CWrite callback function [Display Devices], I2CWrite, PI2C_WRITE, PI2C_WRITE, video/I2CWrite, VideoPort_Functions_3e35f4d8-7c13-4c2c-b0e4-c518bc63e6f6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
-	UserDefined
apilocation: 
-	video.h
apiname: 
-	I2CWrite
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PI2C_WRITE callback


## -description


The <i>I2CWrite</i> function writes data over the <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> channel.


## -prototype


````
PI2C_WRITE I2CWrite;

BOOLEAN I2CWrite(
  _In_ PVOID          HwDeviceExtension,
  _In_ PI2C_CALLBACKS I2CCallbacks,
  _In_ PUCHAR         Buffer,
  _In_ ULONG          Length
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's per-adapter device extension.


### -param I2CCallbacks [in]

Pointer to an <a href="..\video\ns-video-_i2c_callbacks.md">I2C_CALLBACKS</a> structure, containing pointers to miniport driver-defined functions that read and write data and clock lines.


### -param Buffer [in]

Pointer to the data to be written.


### -param Length [in]

Specifies the number of bytes to be written.


## -returns


<i>I2CWrite</i> returns <b>TRUE</b> if the data was successfully written, and <b>FALSE</b> otherwise.



## -remarks


The video port implements this function, which can be accessed through a pointer in the <a href="..\video\ns-video-_video_port_i2c_interface.md">VIDEO_PORT_I2C_INTERFACE</a> structure. 



## -see-also

<a href="..\video\ns-video-_video_port_i2c_interface.md">VIDEO_PORT_I2C_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PI2C_WRITE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

