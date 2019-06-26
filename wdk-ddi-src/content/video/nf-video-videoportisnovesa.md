---
UID: NF:video.VideoPortIsNoVesa
title: VideoPortIsNoVesa function (video.h)
description: The VideoPortIsNoVesa function determines whether a video miniport driver that does not support Plug and Play (PnP) is restricted to legacy VGA resources.
old-location: display\videoportisnovesa.htm
tech.root: display
ms.assetid: e3de4e58-c3e7-426f-bc96-b45cad6b5807
ms.date: 05/10/2018
ms.keywords: VideoPortIsNoVesa, VideoPortIsNoVesa function [Display Devices], VideoPort_Functions_b3e65276-fa78-4599-a3e1-fa097cd86e70.xml, display.videoportisnovesa, video/VideoPortIsNoVesa
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortIsNoVesa
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortIsNoVesa function


## -description


The <b>VideoPortIsNoVesa</b> function determines whether a video miniport driver that does not support Plug and Play (PnP) is restricted to legacy VGA resources.


## -parameters






## -returns



If <b>VideoPortIsNoVesa</b> returns <b>TRUE</b>, then a non-PnP video miniport driver must restrict its hardware access to legacy VGA resources. Otherwise, the video miniport driver is permitted to use non-legacy VGA resources.




## -remarks



This function is useful only to vga.sys, which is a system-supplied video miniport driver that does not support PnP. This function provides no pertinent information to video miniport drivers that support PnP and therefore is no use to IHVs.

If <b>VideoPortIsNoVesa</b> returns <b>TRUE</b>, then the video miniport driver must access the display adapter only through legacy VGA resources (I/O 3B0 through 3DF; memory A0000 through BFFFF). Specifically, if <b>VideoPortIsNoVesa</b> returns <b>TRUE</b>, the video miniport driver must not attempt to call the Int10 functions, which are implemented by the video port driver.

For more information about the Int10 functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Int10 Functions Implemented by the Video Port Driver</a>. 



