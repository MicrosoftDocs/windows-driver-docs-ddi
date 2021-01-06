---
UID: NF:video.VideoPortRegisterBugcheckCallback
title: VideoPortRegisterBugcheckCallback function (video.h)
description: The VideoPortRegisterBugcheckCallback function allows a video miniport driver to register for, or hook, a callback that is invoked when a specified bug check occurs.
old-location: display\videoportregisterbugcheckcallback.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortRegisterBugcheckCallback function"]
ms.keywords: VideoPortRegisterBugcheckCallback, VideoPortRegisterBugcheckCallback function [Display Devices], VideoPort_Functions_ba500792-836e-4181-983c-506bf5608a1c.xml, display.videoportregisterbugcheckcallback, video/VideoPortRegisterBugcheckCallback
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortRegisterBugcheckCallback
 - video/VideoPortRegisterBugcheckCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortRegisterBugcheckCallback
---

# VideoPortRegisterBugcheckCallback function


## -description

The <b>VideoPortRegisterBugcheckCallback</b> function allows a video miniport driver to register for, or hook, a callback that is invoked when a specified bug check occurs.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param BugcheckCode 

[in]
Indicates the bug check code for which to be called back. Currently, the miniport driver can register only for bug check code 0xEA.

### -param Callback 

[in]
Pointer to the miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_bugcheck_callback">HwVidBugcheckCallback</a> function. This function must be nonpaged, and must not reference pageable code or data. The miniport driver can set this parameter to <b>NULL</b> to indicate that the bug check callback should be unhooked.

### -param BugcheckDataSize 

[in]
Indicates the sum of BUGCHECK_DATA_SIZE_RESERVED and the number of bytes of data the miniport driver will provide for inclusion in the dump file. The value of this parameter must be less than or equal to 4000. The miniport driver can set this parameter to zero to indicate that the bug check callback should be unhooked.

## -returns

<b>VideoPortRegisterBugcheckCallback</b> returns NO_ERROR if it succeeds. Otherwise, it returns a status code indicating the nature of the failure.

## -remarks

If you are developing a video miniport driver intended to run on Windows XP or an earlier NT-base operating system, you can use the <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_port_get_proc_address">VideoPortGetProcAddress</a> callback routine to find the address of the <b>VideoPortRegisterBugcheckCallback</b> function. For details, see <a href="/windows-hardware/drivers/display/using-videoportgetprocaddress">Using VideoPortGetProcAddress</a>.

A miniport driver can register for a callback when a specific type of bug check occurs. Currently, only <a href="/windows-hardware/drivers/debugger/bug-check-0xea--thread-stuck-in-device-driver">bug check code 0xEA</a> can be hooked. When the bug check occurs, the minidriver-supplied callback function is called and the miniport driver can append data to the dump file. This is useful for collecting statistical data when direct debugging is not possible.

The value of the <i>BugcheckDataSize </i>parameter must be BUGCHECK_DATA_SIZE_RESERVED bytes larger than the data provided by the miniport driver. For example, suppose the miniport driver provides DUMP_SIZE bytes of data to be written to the dump file. Then the value of <i>BugcheckDataSize</i> should be DUMP_SIZE + BUGCHECK_DATA_SIZE_RESERVED, and that total value must be less than or equal to 4000.

The constant BUGCHECK_DATA_SIZE_RESERVED (defined in <i>video.h</i>) is available in Microsoft Windows Server 2003 and later build environments. In the Windows XP SP1 build environment, use 48 instead of BUGCHECK_DATA_SIZE_RESERVED.

The miniport driver can unregister a previously-registered callback by calling this function, specifying <b>NULL</b> for the <i>Callback</i> parameter, or zero for the <i>DataSize</i> parameter.

For more information, see <a href="/windows-hardware/drivers/display/video-port-driver-support-for-bug-check-callbacks">Video Port Driver Support for Bug Check Callbacks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_bugcheck_callback">HwVidBugcheckCallback</a>
