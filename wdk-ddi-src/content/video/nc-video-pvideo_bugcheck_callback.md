---
UID: NC:video.PVIDEO_BUGCHECK_CALLBACK
title: PVIDEO_BUGCHECK_CALLBACK
author: windows-driver-content
description: The HwVidBugcheckCallback function enables the miniport driver to append data to a dump file when a bug check occurs.
old-location: display\hwvidbugcheckcallback.htm
old-project: display
ms.assetid: 1223534f-a89c-45b4-b07d-75c2c8383b73
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.hwvidbugcheckcallback, HwVidBugcheckCallback callback function [Display Devices], HwVidBugcheckCallback, PVIDEO_BUGCHECK_CALLBACK, PVIDEO_BUGCHECK_CALLBACK, video/HwVidBugcheckCallback, VideoMiniport_Functions_d3dcce93-d172-4948-8cc5-395dd2a1f9a5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	video.h
apiname: 
-	HwVidBugcheckCallback
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PVIDEO_BUGCHECK_CALLBACK callback


## -description


The <i>HwVidBugcheckCallback</i> function enables the miniport driver to append data to a dump file when a bug check occurs.


## -prototype


````
PVIDEO_BUGCHECK_CALLBACK HwVidBugcheckCallback;

VOID HwVidBugcheckCallback(
  _In_ PVOID  HwDeviceExtension,
  _In_ ULONG  BugcheckCode,
  _In_ PUCHAR Buffer,
  _In_ ULONG  BufferSize
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param BugcheckCode [in]

Specifies a <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check code</a>.


### -param Buffer [in]

Pointer to the memory location where the miniport driver can store the data that is to be appended to the dump file.


### -param BufferSize [in]

Specifies the size, in bytes, of the buffer pointed to by the <i>Buffer</i> parameter.


## -returns


None



## -remarks


This function is available in Windows XP SP1 and later. 

This function is called when a bug check occurs. The miniport driver can collect data that is to be appended to the dump file and write this data to the buffer. The driver must not write more than <i>BufferSize</i> bytes to the buffer.

A video miniport driver registers the <i>HwVidBugcheckCallback</i> function by calling the <a href="..\video\nf-video-videoportregisterbugcheckcallback.md">VideoPortRegisterBugcheckCallback</a> function. The <b>VideoPortRegisterBugcheckCallback</b> function exposes this video miniport driver-supplied callback to the system.

To facilitate system recovery after a bug check, any registers that are accessed by this function must not impede the ability of the hardware to transfer to fallback mode, regardless of the state of the device. Also, the function <i>must</i> return control to its caller.

Because a system can consist of multiple video miniport drivers, venders should add an identifying string to the data that this function appends to the dump file. 

The function is called at raised IRQL and must not attempt to access pageable code or data.



## -see-also

<a href="..\video\nf-video-videoportregisterbugcheckcallback.md">VideoPortRegisterBugcheckCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_BUGCHECK_CALLBACK callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

