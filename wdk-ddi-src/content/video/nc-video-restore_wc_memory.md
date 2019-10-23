---
UID: NC:video.RESTORE_WC_MEMORY
title: RESTORE_WC_MEMORY (video.h)
description: The VideoPortRestoreWCMemory callback routine restores Write Combined video memory from a protected state after the VideoPortProtectWCMemory callback routine was called.
old-location: display\videoportrestorewcmemory.htm
tech.root: display
ms.assetid: 8fa0be0c-04ce-41ab-93dd-6dc9e8daa356
ms.date: 05/10/2018
ms.keywords: RESTORE_WC_MEMORY, RESTORE_WC_MEMORY callback, VideoPortRestoreWCMemory, VideoPortRestoreWCMemory callback function [Display Devices], VideoPort_Functions_88c8ebcc-40d1-4883-9e99-eac1aab0c6c7.xml, display.videoportrestorewcmemory, video/VideoPortRestoreWCMemory
ms.topic: callback
f1_keywords:
 - "video/VideoPortRestoreWCMemory"
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
- VideoPortRestoreWCMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# RESTORE_WC_MEMORY callback function


## -description


The <i>VideoPortRestoreWCMemory</i> callback routine restores Write Combined video memory from a protected state after the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-protect_wc_memory">VideoPortProtectWCMemory</a> callback routine was called.


## -parameters




### -param Context [in]

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>. It typically points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> buffer.


### -param HwDeviceExtension [in]

Pointer to the miniport driver's hardware device extension.


## -returns



<i>VideoPortRestoreWCMemory</i> returns NO_ERROR if it successfully restored Write Combined video memory; otherwise, it returns an error status of ERROR_INVALID_FUNCTION or ERROR_NOT_ENOUGH_MEMORY.




## -remarks



After the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-protect_wc_memory">VideoPortProtectWCMemory</a> callback routine is called, the CPU cannot write to Write Combined memory until <i>VideoPortRestoreWCMemory</i> is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-protect_wc_memory">VideoPortProtectWCMemory</a>
 

 

