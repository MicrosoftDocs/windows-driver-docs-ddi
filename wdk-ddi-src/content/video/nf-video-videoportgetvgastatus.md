---
UID: NF:video.VideoPortGetVgaStatus
title: VideoPortGetVgaStatus function
author: windows-driver-content
description: The VideoPortGetVgaStatus function detects whether the calling device is decoding a VGA I/O address.
old-location: display\videoportgetvgastatus.htm
old-project: display
ms.assetid: 5a2bb69c-b10a-41bb-a92a-de7add3ca2c5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortGetVgaStatus
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
req.alt-api: VideoPortGetVgaStatus
req.alt-loc: Videoprt.sys
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
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetVgaStatus function



## -description
The <b>VideoPortGetVgaStatus</b> function detects whether the calling device is decoding a VGA I/O address.



## -syntax

````
VP_STATUS VideoPortGetVgaStatus(
        PVOID  HwDeviceExtension,
  _Out_ PULONG VgaStatus
);
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's device extension.


### -param VgaStatus [out]

Pointer to the resulting VGA status. A value of zero (0) indicates that VGA is not enabled; a value of one (1) indicates that VGA is enabled.


## -returns
<b>VideoPortGetVgaStatus</b> returns one of the following values:
<dl>
<dt><b>NO_ERROR</b></dt>
</dl>The function completed successfully.
<dl>
<dt><b>ERROR_INVALID_FUNCTION</b></dt>
</dl>The device was not a PCI device.

 


## -remarks
The <b>VideoPortGetVgaStatus</b> function is mainly used to determine whether a device is the sole VGA-enabled device in a <a href="https://msdn.microsoft.com/ba15af67-94c0-4c37-8b3d-b1472e731d88">multiple monitor</a> system. </p>