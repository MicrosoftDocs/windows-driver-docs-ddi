---
UID: NC:hdaudio.PUNREGISTER_EVENT_CALLBACK
title: PUNREGISTER_EVENT_CALLBACK
author: windows-driver-content
description: The UnregisterEventCallback routine deletes the registration of an event callback that was previously registered by a call to RegisterEventCallback.The function pointer type for an UnregisterEventCallback routine is defined as follows.
old-location: audio\unregistereventcallback.htm
old-project: audio
ms.assetid: 698017a0-13d5-4ed5-a1ce-1a50a62135e0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PUNREGISTER_EVENT_CALLBACK, UnregisterEventCallback, UnregisterEventCallback callback function [Audio Devices], aud-prop2_9d6c50d7-56ac-4364-9a1e-74ea0d934046.xml, audio.unregistereventcallback, hdaudio/UnregisterEventCallback
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
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# PUNREGISTER_EVENT_CALLBACK callback


## -description


The <i>UnregisterEventCallback</i> routine deletes the registration of an event callback that was previously registered by a call to <a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a>.

The function pointer type for an <i>UnregisterEventCallback</i> routine is defined as follows.


## -prototype


````
PUNREGISTER_EVENT_CALLBACK UnregisterEventCallback;

NTSTATUS UnregisterEventCallback(
  _In_ PVOID _context,
  _In_ UCHAR Tag
)
{ ... }
````


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param Tag [in]

Specifies the tag value that was associated with the callback by the preceding call to <a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a>.


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

<a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">RegisterEventCallback</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PUNREGISTER_EVENT_CALLBACK callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

