---
UID: NS:video._VPOSVERSIONINFO
title: _VPOSVERSIONINFO (video.h)
description: The VPOSVERSIONINFO structure contains version information about the currently running operating system.
old-location: display\vposversioninfo.htm
tech.root: display
ms.assetid: b6335df5-81d9-4a00-8e97-0ebebb987d32
ms.date: 05/10/2018
ms.keywords: "*PVPOSVERSIONINFO, PVPOSVERSIONINFO, PVPOSVERSIONINFO structure pointer [Display Devices], VPOSVERSIONINFO, VPOSVERSIONINFO structure [Display Devices], Video_Structs_893105be-4f14-4903-aae1-85ffe8ef8a2b.xml, _VPOSVERSIONINFO, display.vposversioninfo, video/PVPOSVERSIONINFO, video/VPOSVERSIONINFO"
ms.topic: struct
f1_keywords:
 - "video/VPOSVERSIONINFO"
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
- VPOSVERSIONINFO
product:
- Windows
targetos: Windows
req.typenames: VPOSVERSIONINFO, *PVPOSVERSIONINFO
---

# _VPOSVERSIONINFO structure


## -description


The VPOSVERSIONINFO structure contains version information about the currently running operating system.


## -struct-fields




### -field Size

Specifies the size, in bytes, of the VPOSVERSIONINFO structure.


### -field MajorVersion

Specifies the major version number of the operating system. For example, for Windows 2000, the major version number is five. For Windows XP, the major version number is six.


### -field MinorVersion

Specifies the minor version number of the operating system. For example, for Windows 2000, the minor version number is zero.


### -field BuildNumber

Specifies the build number of the operating system.


### -field ServicePackMajor

Specifies the major version number of the latest Service Pack installed on the operating system. For example, for Service Pack 3, the major version number is three.


### -field ServicePackMinor

Specifies the minor version number of the latest Service Pack installed on the operating system. For example, for Service Pack 3, the minor version number is zero.


## -remarks



This structure is available in Windows XP and later.

To obtain version information about the currently running operating system, a video miniport driver would call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetversion">VideoPortGetVersion</a> function, which fills in this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetversion">VideoPortGetVersion</a>
 

 

