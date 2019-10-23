---
UID: NC:video.PINT10_CALL_BIOS
title: PINT10_CALL_BIOS (video.h)
description: The Int10CallBios function allows a miniport driver to call the kernel to perform an INT 10h operation, causing the BIOS ROM code on the device to execute natively.
old-location: display\int10callbios.htm
tech.root: display
ms.assetid: 994a73bc-81a1-4d73-959c-cc89b242c073
ms.date: 05/10/2018
ms.keywords: Int10CallBios, Int10CallBios callback function [Display Devices], PINT10_CALL_BIOS, PINT10_CALL_BIOS callback, VideoPort_Functions_7a9921fa-ea1e-49fa-8881-ea0792d91123.xml, display.int10callbios, video/Int10CallBios
ms.topic: callback
f1_keywords:
 - "video/Int10CallBios"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- video.h
api_name:
- Int10CallBios
product:
- Windows
targetos: Windows
req.typenames: 
---

# PINT10_CALL_BIOS callback function


## -description


The <i>Int10CallBios</i> function allows a miniport driver to call the kernel to perform an INT 10h operation, causing the BIOS ROM code on the device to execute natively.


## -parameters




### -param Context

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a> returns.


### -param BiosArguments

Pointer to a video miniport driver-initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_int10_bios_arguments">INT10_BIOS_ARGUMENTS</a> structure containing the values of the x86 registers. Any registers that are not needed in the INT10 BIOS call should be set to 0. When the function returns, some members of the INT10_BIOS_ARGUMENTS structures can have different values than before the call.


## -returns



The <b>Int10CallBios</b> function returns NO_ERROR upon success. Otherwise it returns an appropriate error code.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a> structure. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a>
 

 

