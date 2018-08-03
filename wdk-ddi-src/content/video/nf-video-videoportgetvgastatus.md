---
UID: NF:video.VideoPortGetVgaStatus
title: VideoPortGetVgaStatus function
author: windows-driver-content
description: The VideoPortGetVgaStatus function detects whether the calling device is decoding a VGA I/O address.
old-location: display\videoportgetvgastatus.htm
tech.root: display
ms.assetid: 5a2bb69c-b10a-41bb-a92a-de7add3ca2c5
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: VideoPortGetVgaStatus, VideoPortGetVgaStatus function [Display Devices], VideoPort_Functions_f3e43fe4-2e50-48d4-b185-f44e2a2adb31.xml, display.videoportgetvgastatus, video/VideoPortGetVgaStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	VideoPortGetVgaStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetVgaStatus function


## -description


The <b>VideoPortGetVgaStatus</b> function detects whether the calling device is decoding a VGA I/O address.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param VgaStatus [out]

Pointer to the resulting VGA status. A value of zero (0) indicates that VGA is not enabled; a value of one (1) indicates that VGA is enabled.


## -returns



<b>VideoPortGetVgaStatus</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NO_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The function completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_INVALID_FUNCTION</b></dt>
</dl>
</td>
<td width="60%">
The device was not a PCI device.

</td>
</tr>
</table>
 




## -remarks



The <b>VideoPortGetVgaStatus</b> function is mainly used to determine whether a device is the sole VGA-enabled device in a <a href="https://msdn.microsoft.com/ba15af67-94c0-4c37-8b3d-b1472e731d88">multiple monitor</a> system. 



