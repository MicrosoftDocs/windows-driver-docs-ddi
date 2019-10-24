---
UID: NS:video._INT10_BIOS_ARGUMENTS
title: _INT10_BIOS_ARGUMENTS (video.h)
description: The INT10_BIOS_ARGUMENTS structure is used to support full-screen MS-DOS application INT10 calls. It contains nine of the high-end x86 microprocessor registers.
old-location: display\int10_bios_arguments.htm
tech.root: display
ms.assetid: 66fc9bd4-da47-4cd1-baf2-b536272ea28e
ms.date: 05/10/2018
ms.keywords: "*PINT10_BIOS_ARGUMENTS, INT10_BIOS_ARGUMENTS, INT10_BIOS_ARGUMENTS structure [Display Devices], PINT10_BIOS_ARGUMENTS, PINT10_BIOS_ARGUMENTS structure pointer [Display Devices], Video_Structs_986b625a-f1b4-401e-b2db-99463c21e8f9.xml, _INT10_BIOS_ARGUMENTS, display.int10_bios_arguments, video/INT10_BIOS_ARGUMENTS, video/PINT10_BIOS_ARGUMENTS"
ms.topic: struct
f1_keywords:
 - "video/INT10_BIOS_ARGUMENTS"
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
- INT10_BIOS_ARGUMENTS
product:
- Windows
targetos: Windows
req.typenames: INT10_BIOS_ARGUMENTS, *PINT10_BIOS_ARGUMENTS
---

# _INT10_BIOS_ARGUMENTS structure


## -description


The INT10_BIOS_ARGUMENTS structure is used to support full-screen MS-DOS application INT10 calls. It contains nine of the high-end x86 microprocessor registers.


## -struct-fields




### -field Eax


### -field Ebx


### -field Ecx


### -field Edx


### -field Esi


### -field Edi


### -field Ebp

Are seven of the x86 microprocessor registers.


### -field SegDs


### -field SegEs

Are two of the x86 microprocessor segment registers.


## -remarks



The first seven members of the INT10_BIOS_ARGUMENTS structure are identical to those of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_x86_bios_arguments">VIDEO_x86_BIOS_ARGUMENTS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pint10_call_bios">Int10CallBios</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_x86_bios_arguments">VIDEO_x86_BIOS_ARGUMENTS</a>
 

 

