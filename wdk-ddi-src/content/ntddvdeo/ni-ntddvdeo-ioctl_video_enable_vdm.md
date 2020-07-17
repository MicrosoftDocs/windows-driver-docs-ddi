---
UID: NI:ntddvdeo.IOCTL_VIDEO_ENABLE_VDM
title: IOCTL_VIDEO_ENABLE_VDM (ntddvdeo.h)
description: This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.
old-location: display\ioctl_video_enable_vdm.htm
tech.root: display
ms.assetid: 45a5ab64-1b34-4f48-bbe3-285016e9c16e
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_ENABLE_VDM IOCTL"]
ms.keywords: IOCTL_VIDEO_ENABLE_VDM, IOCTL_VIDEO_ENABLE_VDM control, IOCTL_VIDEO_ENABLE_VDM control code [Display Devices], Video_IOCTLs_d0e75fac-0604-49f5-9293-3455659ab821.xml, display.ioctl_video_enable_vdm, ntddvdeo/IOCTL_VIDEO_ENABLE_VDM
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_ENABLE_VDM"
 - "IOCTL_VIDEO_ENABLE_VDM"
req.header: ntddvdeo.h
req.include-header: 
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
- Ntddvdeo.h
api_name:
- IOCTL_VIDEO_ENABLE_VDM
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_ENABLE_VDM IOCTL


## -description



This IOCTL is not handled by video miniport drivers. It is handled entirely by the system-supplied video port driver.




## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).




## -remarks



<div class="alert"><b>Note</b>    This IOCTL is obsolete in Windows Vista.</div>
<div> </div>


