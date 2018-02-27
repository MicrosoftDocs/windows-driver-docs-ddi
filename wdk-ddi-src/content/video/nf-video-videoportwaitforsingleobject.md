---
UID: NF:video.VideoPortWaitForSingleObject
title: VideoPortWaitForSingleObject function
author: windows-driver-content
description: The VideoPortWaitForSingleObject function puts the current thread into a wait state until the given dispatch object is set to the signaled state, or (optionally) until the wait times out.
old-location: display\videoportwaitforsingleobject.htm
old-project: display
ms.assetid: 574aa79e-c8ef-44de-8d0b-a550698a32e0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VideoPortWaitForSingleObject, VideoPortWaitForSingleObject function [Display Devices], VideoPort_Functions_a1678f59-0c1c-4b0a-b1e6-2dbb71c8a7c2.xml, display.videoportwaitforsingleobject, video/VideoPortWaitForSingleObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortWaitForSingleObject
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortWaitForSingleObject function


## -description


The <b>VideoPortWaitForSingleObject</b> function puts the current thread into a wait state until the given dispatch object is set to the signaled state, or (optionally) until the wait times out.


## -syntax


````
VP_STATUS VideoPortWaitForSingleObject(
  _In_ PVOID          HwDeviceExtension,
  _In_ PVOID          Object,
  _In_ PLARGE_INTEGER Timeout
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param Object [in]

Pointer to the event object.


### -param Timeout [in]

(Optional) Pointer to a time-out value that specifies the absolute or relative time at which the wait is to be completed. A negative value specifies a wait interval relative to the current time. The value should be expressed in units of 100 nanoseconds. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.


## -returns



<b>VideoPortWaitForSingleObject</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters is invalid or the call attempted to wait for a mapped user event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NO_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The event object specified in the <i>pObject</i> parameter satisfied the wait.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>WAIT_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
A time-out occurred before the event object was set to the signaled state. This value can be returned when the specified set of wait conditions cannot be immediately met and <i>Timeout</i> is set to zero.

</td>
</tr>
</table>
 




## -remarks



The miniport driver should not attempt to wait for a mapped user event.

Callers of <b>VideoPortWaitForSingleObject</b> must be running at IRQL &lt;= DISPATCH_LEVEL. Usually, the caller will be running at IRQL = PASSIVE_LEVEL and in a nonarbitrary thread context. A call to this function while running at IRQL = DISPATCH_LEVEL is valid if and only if the caller specifies a <i>Timeout</i> value of zero. That is, a miniport driver must not wait for a nonzero interval at IRQL = DISPATCH_LEVEL.



