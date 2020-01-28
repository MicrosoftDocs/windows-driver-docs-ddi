---
UID: NS:video._VIDEO_X86_BIOS_ARGUMENTS
title: _VIDEO_X86_BIOS_ARGUMENTS (video.h)
description: The VIDEO_x86_BIOS_ARGUMENTS structure is used to support full-screen MS-DOS application INT10 calls. It contains seven of the high-end x86 microprocessor registers.
old-location: display\video_x86_bios_arguments.htm
tech.root: display
ms.assetid: c0404803-d8a5-4698-a725-12c659cbcaab
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_X86_BIOS_ARGUMENTS, PVIDEO_X86_BIOS_ARGUMENTS, PVIDEO_X86_BIOS_ARGUMENTS structure pointer [Display Devices], VIDEO_X86_BIOS_ARGUMENTS, VIDEO_X86_BIOS_ARGUMENTS structure [Display Devices], VIDEO_x86_BIOS_ARGUMENTS, VIDEO_x86_BIOS_ARGUMENTS structure [Display Devices], Video_Structs_6e82199c-1448-483c-ab53-73590564b165.xml, _VIDEO_X86_BIOS_ARGUMENTS, display.video_x86_bios_arguments, video/PVIDEO_X86_BIOS_ARGUMENTS, video/VIDEO_X86_BIOS_ARGUMENTS"
f1_keywords:
 - "video/VIDEO_X86_BIOS_ARGUMENTS"
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
- VIDEO_X86_BIOS_ARGUMENTS
product:
- Windows
targetos: Windows
req.typenames: VIDEO_X86_BIOS_ARGUMENTS, *PVIDEO_X86_BIOS_ARGUMENTS
---

# _VIDEO_X86_BIOS_ARGUMENTS structure


## -description


The VIDEO_x86_BIOS_ARGUMENTS structure is used to support full-screen MS-DOS application INT10 calls. It contains seven of the high-end x86 microprocessor registers.


## -struct-fields




### -field Eax


### -field Ebx


### -field Ecx


### -field Edx


### -field Esi


### -field Edi


### -field Ebp

Are the seven x86 microprocessor registers.


## -remarks



MS-DOS INT10s are usually "set mode" requests for the video adapter. Each value is put in the appropriate register and an INT10 call is performed by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportint10">VideoPortInt10</a>.

A miniport driver should <i>not</i> set a segment:offset-type pointer in any member of this structure. Such an address is interpreted as an unsigned DWORD value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportint10">VideoPortInt10</a>
 

 

