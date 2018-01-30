---
UID: NC:video.PVIDEO_PORT_GET_PROC_ADDRESS
title: PVIDEO_PORT_GET_PROC_ADDRESS
author: windows-driver-content
description: The VideoPortGetProcAddress callback routine retrieves the address of a Windows 2000 or later video port driver function.
old-location: display\videoportgetprocaddress.htm
old-project: display
ms.assetid: f4263cc6-2065-475a-b618-6a5735c5f66e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoportgetprocaddress, VideoPortGetProcAddress callback function [Display Devices], VideoPortGetProcAddress, PVIDEO_PORT_GET_PROC_ADDRESS, PVIDEO_PORT_GET_PROC_ADDRESS, video/VideoPortGetProcAddress, VideoPort_Functions_303c9139-f7bd-4334-9379-ca5e167e4618.xml
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
-	VideoPortGetProcAddress
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
---

# PVIDEO_PORT_GET_PROC_ADDRESS callback


## -description


The <i>VideoPortGetProcAddress</i> callback routine retrieves the address of a Windows 2000 or later video port driver function.


## -prototype


````
PVIDEO_PORT_GET_PROC_ADDRESS VideoPortGetProcAddress;

PVOID VideoPortGetProcAddress(
  _In_ PVOID  HwDeviceExtension,
  _In_ PUCHAR FunctionName
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's hardware device extension.


### -param FunctionName [in]

Pointer to a null-terminated ASCII string that contains the name of the function being searched for.


## -returns


<i>VideoPortGetProcAddress</i> returns a pointer to the function specified in the <i>FunctionName </i>parameter, if it exists. If that function does not exist, this function returns <b>NULL</b>.



## -remarks


<i>VideoPortGetProcAddress</i> makes it possible for a video miniport driver to gain access to video port driver functions without linking to them directly. This enables a miniport driver to take full advantage of Windows 2000 and later features but still be able to load on earlier NT-based operating system versions. For an example of how to use <i>VideoPortGetProcAddress</i>, see <a href="https://msdn.microsoft.com/48dace7e-7ba3-48bf-9788-469ff42f6fe3">Using VideoPortGetProcAddress</a>.

The <b>VideoPortGetProcAddress</b> member of the <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> structure contains the address of this callback routine. 



## -see-also

<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_PORT_GET_PROC_ADDRESS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

