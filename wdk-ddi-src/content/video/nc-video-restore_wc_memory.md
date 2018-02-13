---
UID: NC:video.RESTORE_WC_MEMORY
title: RESTORE_WC_MEMORY
author: windows-driver-content
description: The VideoPortRestoreWCMemory callback routine restores Write Combined video memory from a protected state after the VideoPortProtectWCMemory callback routine was called.
old-location: display\videoportrestorewcmemory.htm
old-project: display
ms.assetid: 8fa0be0c-04ce-41ab-93dd-6dc9e8daa356
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoportrestorewcmemory, VideoPortRestoreWCMemory callback function [Display Devices], VideoPortRestoreWCMemory, RESTORE_WC_MEMORY, RESTORE_WC_MEMORY, video/VideoPortRestoreWCMemory, VideoPort_Functions_88c8ebcc-40d1-4883-9e99-eac1aab0c6c7.xml
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	video.h
apiname:
-	VideoPortRestoreWCMemory
product: Windows
targetos: Windows
req.typenames: "*PVHF_CONFIG, VHF_CONFIG"
req.product: Windows 10 or later.
---

# RESTORE_WC_MEMORY callback


## -description


The <i>VideoPortRestoreWCMemory</i> callback routine restores Write Combined video memory from a protected state after the <a href="..\video\nc-video-protect_wc_memory.md">VideoPortProtectWCMemory</a> callback routine was called.


## -prototype


````
RESTORE_WC_MEMORY VideoPortRestoreWCMemory;

VP_STATUS VideoPortRestoreWCMemory(
  _In_ PVOID Context,
  _In_ PVOID HwDeviceExtension
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>. It typically points to the <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> buffer.


### -param HwDeviceExtension [in]

Pointer to the miniport driver's hardware device extension.


## -returns



<i>VideoPortRestoreWCMemory</i> returns NO_ERROR if it successfully restored Write Combined video memory; otherwise, it returns an error status of ERROR_INVALID_FUNCTION or ERROR_NOT_ENOUGH_MEMORY.




## -remarks



After the <a href="..\video\nc-video-protect_wc_memory.md">VideoPortProtectWCMemory</a> callback routine is called, the CPU cannot write to Write Combined memory until <i>VideoPortRestoreWCMemory</i> is called.




## -see-also

<a href="..\video\nc-video-protect_wc_memory.md">VideoPortProtectWCMemory</a>



<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20RESTORE_WC_MEMORY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

