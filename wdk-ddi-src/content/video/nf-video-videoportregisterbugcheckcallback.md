---
UID: NF:video.VideoPortRegisterBugcheckCallback
title: VideoPortRegisterBugcheckCallback function
author: windows-driver-content
description: The VideoPortRegisterBugcheckCallback function allows a video miniport driver to register for, or hook, a callback that is invoked when a specified bug check occurs.
old-location: display\videoportregisterbugcheckcallback.htm
old-project: display
ms.assetid: 55b2d603-f3ac-4a7a-91f5-83d908d1e14b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VideoPortRegisterBugcheckCallback, VideoPortRegisterBugcheckCallback function [Display Devices], VideoPort_Functions_ba500792-836e-4181-983c-506bf5608a1c.xml, display.videoportregisterbugcheckcallback, video/VideoPortRegisterBugcheckCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP SP1 and later versions of the Windows operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortRegisterBugcheckCallback
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortRegisterBugcheckCallback function


## -description


The <b>VideoPortRegisterBugcheckCallback</b> function allows a video miniport driver to register for, or hook, a callback that is invoked when a specified bug check occurs.


## -syntax


````
VP_STATUS VideoPortRegisterBugcheckCallback(
  _In_ PVOID                    HwDeviceExtension,
  _In_ ULONG                    BugcheckCode,
  _In_ PVIDEO_BUGCHECK_CALLBACK Callback,
  _In_ ULONG                    BugcheckDataSize
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param BugcheckCode [in]

Indicates the bug check code for which to be called back. Currently, the miniport driver can register only for bug check code 0xEA.


### -param Callback [in]

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_bugcheck_callback.md">HwVidBugcheckCallback</a> function. This function must be nonpaged, and must not reference pageable code or data. The miniport driver can set this parameter to <b>NULL</b> to indicate that the bug check callback should be unhooked. 


### -param BugcheckDataSize [in]

Indicates the sum of BUGCHECK_DATA_SIZE_RESERVED and the number of bytes of data the miniport driver will provide for inclusion in the dump file. The value of this parameter must be less than or equal to 4000. The miniport driver can set this parameter to zero to indicate that the bug check callback should be unhooked.


## -returns



<b>VideoPortRegisterBugcheckCallback</b> returns NO_ERROR if it succeeds. Otherwise, it returns a status code indicating the nature of the failure. 




## -remarks



If you are developing a video miniport driver intended to run on Windows XP or an earlier NT-base operating system, you can use the <a href="..\video\nc-video-pvideo_port_get_proc_address.md">VideoPortGetProcAddress</a> callback routine to find the address of the <b>VideoPortRegisterBugcheckCallback</b> function. For details, see <a href="https://msdn.microsoft.com/48dace7e-7ba3-48bf-9788-469ff42f6fe3">Using VideoPortGetProcAddress</a>.

A miniport driver can register for a callback when a specific type of bug check occurs. Currently, only <a href="https://msdn.microsoft.com/f3d6acaf-3445-4fc3-b4ed-b72a74a32b57">bug check code 0xEA</a> can be hooked. When the bug check occurs, the minidriver-supplied callback function is called and the miniport driver can append data to the dump file. This is useful for collecting statistical data when direct debugging is not possible.

The value of the <i>BugcheckDataSize </i>parameter must be BUGCHECK_DATA_SIZE_RESERVED bytes larger than the data provided by the miniport driver. For example, suppose the miniport driver provides DUMP_SIZE bytes of data to be written to the dump file. Then the value of <i>BugcheckDataSize</i> should be DUMP_SIZE + BUGCHECK_DATA_SIZE_RESERVED, and that total value must be less than or equal to 4000.

The constant BUGCHECK_DATA_SIZE_RESERVED (defined in <i>video.h</i>) is available in Microsoft Windows Server 2003 and later build environments. In the Windows XP SP1 build environment, use 48 instead of BUGCHECK_DATA_SIZE_RESERVED.

The miniport driver can unregister a previously-registered callback by calling this function, specifying <b>NULL</b> for the <i>Callback</i> parameter, or zero for the <i>DataSize</i> parameter.

For more information, see <a href="https://msdn.microsoft.com/181fd4f2-feed-4759-80a7-aec97b9094b3">Video Port Driver Support for Bug Check Callbacks</a>.




## -see-also

<a href="..\video\nc-video-pvideo_bugcheck_callback.md">HwVidBugcheckCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortRegisterBugcheckCallback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

