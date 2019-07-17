---
UID: NC:video.PROTECT_WC_MEMORY
title: PROTECT_WC_MEMORY (video.h)
description: The VideoPortProtectWCMemory callback routine protects Write Combined (WC) video memory from being accessed by the CPU.
old-location: display\videoportprotectwcmemory.htm
tech.root: display
ms.assetid: 0cee4f4d-4d9c-44be-94ad-459000f2adb1
ms.date: 05/10/2018
ms.keywords: PROTECT_WC_MEMORY, PROTECT_WC_MEMORY callback, VideoPortProtectWCMemory, VideoPortProtectWCMemory callback function [Display Devices], VideoPort_Functions_5aead504-6c27-4b86-95e0-b4ec1b2b3e7d.xml, display.videoportprotectwcmemory, video/VideoPortProtectWCMemory
ms.topic: callback
f1_keywords:
 - "video/VideoPortProtectWCMemory"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- video.h
api_name:
- VideoPortProtectWCMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTECT_WC_MEMORY callback function


## -description


The <i>VideoPortProtectWCMemory</i> callback routine protects Write Combined (WC) video memory from being accessed by the CPU.


## -parameters




### -param Context [in]

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>. It typically points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> buffer.


### -param HwDeviceExtension [in]

Pointer to the miniport driver's hardware device extension.


## -returns



<i>VideoPortProtectWCMemory</i> returns NO_ERROR if it successfully protects Write Combined video memory; otherwise, it returns an error status of ERROR_INVALID_FUNCTION or ERROR_NOT_ENOUGH_MEMORY.




## -remarks



After <i>VideoPortProtectWCMemory</i> is called, the CPU cannot write to Write Combined (WC) memory until the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-restore_wc_memory">VideoPortRestoreWCMemory</a> callback routine is called.

When WC memory protection is no longer required, the display miniport driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-restore_wc_memory">VideoPortRestoreWCMemory</a> to restore CPU access to WC memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-restore_wc_memory">VideoPortRestoreWCMemory</a>
 

 

