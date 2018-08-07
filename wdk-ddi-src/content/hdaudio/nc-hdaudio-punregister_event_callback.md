---
UID: NC:hdaudio.PUNREGISTER_EVENT_CALLBACK
title: PUNREGISTER_EVENT_CALLBACK
author: windows-driver-content
description: The UnregisterEventCallback routine deletes the registration of an event callback that was previously registered by a call to RegisterEventCallback.The function pointer type for an UnregisterEventCallback routine is defined as follows.
old-location: audio\unregistereventcallback.htm
tech.root: audio
ms.assetid: 698017a0-13d5-4ed5-a1ce-1a50a62135e0
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: PUNREGISTER_EVENT_CALLBACK, PUNREGISTER_EVENT_CALLBACK callback, UnregisterEventCallback, UnregisterEventCallback callback function [Audio Devices], aud-prop2_9d6c50d7-56ac-4364-9a1e-74ea0d934046.xml, audio.unregistereventcallback, hdaudio/UnregisterEventCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	hdaudio.h
api_name:
-	UnregisterEventCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PUNREGISTER_EVENT_CALLBACK callback function


## -description


The <i>UnregisterEventCallback</i> routine deletes the registration of an event callback that was previously registered by a call to <a href="https://msdn.microsoft.com/0f94146b-aa60-4106-aba6-0f1cb3e53008">RegisterEventCallback</a>.

The function pointer type for an <i>UnregisterEventCallback</i> routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536413">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="https://msdn.microsoft.com/library/windows/hardware/ff536418">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536416">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param Tag [in]

Specifies the tag value that was associated with the callback by the preceding call to <a href="https://msdn.microsoft.com/0f94146b-aa60-4106-aba6-0f1cb3e53008">RegisterEventCallback</a>.


## -returns



<i>UnregisterEventCallback</i> returns STATUS_SUCCESS if the call succeeds in changing the DMA engines' states. Otherwise, the routine returns an appropriate error code. The following table shows a possible return status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the specified tag is not valid.

</td>
</tr>
</table>
 




## -remarks



Before calling this routine, the function driver is responsible for programming the codec or codecs to remove the association of the callback with the specified tag.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536413">HDAUDIO_BUS_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536416">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536418">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="https://msdn.microsoft.com/0f94146b-aa60-4106-aba6-0f1cb3e53008">RegisterEventCallback</a>
 

 

