---
UID: NF:ks.KsPinGenerateEvents
title: KsPinGenerateEvents function
author: windows-driver-content
description: The KsPinGenerateEvents function generates events of an indicated type that are present in Pin's event list.
old-location: stream\kspingenerateevents.htm
tech.root: stream
ms.assetid: c2137849-aff0-4bf7-abab-b92e17aaef70
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsPinGenerateEvents, KsPinGenerateEvents function [Streaming Media Devices], avfunc_4bc7a2d8-139f-4f6e-b69c-46e05d8302e3.xml, ks/KsPinGenerateEvents, stream.kspingenerateevents
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL (See Remarks)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsPinGenerateEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGenerateEvents function


## -description


The<b> KsPinGenerateEvents</b> function generates events of an indicated type that are present in <i>Pin</i>'s event list.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure on which to generate events. 


### -param EventSet [in, optional]

A pointer to the event set GUID to match to determine which events to generate. If this parameter is <b>NULL</b>, set GUID is not taken into account for determining matching events.


### -param EventId [in]

The event ID to match to determine which events to generate.


### -param DataSize [in]

The size in bytes of the data with which to generate the data event.


### -param Data [in, optional]

A pointer to a data buffer. Specify if generating a data event.


### -param CallBack [in, optional]

A pointer to a caller-specified function that is called to determine whether a given event should be generated. If <b>NULL</b>, no callback verification is performed to determine whether an event should be generated (only <i>EventSet </i>and <i>EventId</i> are used). Prototype as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  BOOLEAN CallBack
(IN PVOID Context,
    IN PKSEVENT_ENTRY EventEntry); </pre>
</td>
</tr>
</table></span></div>
<b>KsPinGenerateEvents</b> passes the <i>CallBackContext</i> parameter unchanged as the <i>Context</i> parameter for the callback. The callback function returns <b>TRUE</b> if <i>EventEntry</i> should be generated. Otherwise, it returns <b>FALSE</b>. 


### -param CallBackContext [in, optional]

A pointer to a caller-specified context that is passed to the callback function <i>CallBack</i>. 


## -returns



None




## -remarks



When calling this function, a minidriver must place <i>Data</i> and <i>CallBackContext</i> in a locked, nonpageable data segment. The <i>CallBack</i> is made at DISPATCH_LEVEL. The callback function must be in a locked segment and must be prepared to run at IRQL = DISPATCH_LEVEL. Note that there is an additional issue in DX8 <i>only</i>: <i>EventSet</i> must be in a locked data segment.

This is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562597">KsGenerateEvents</a>, which performs the necessary typecasting. Minidrivers should usually call this version instead of directly calling <b>KsGenerateEvents</b>.

An event is generated if the following three conditions hold:

<ul>
<li>
The event is present in <i>Pin's </i>event list and <i>EventId </i>matches the event's ID.

</li>
<li>
<i>EventSet</i> either matches the event's set GUID or is <b>NULL</b>.

</li>
<li>
<i>CallBack </i>is either <b>NULL</b> or authorizes the match.

</li>
</ul>
For more information, see <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a> and <a href="https://msdn.microsoft.com/3eaa1d65-8417-4a07-b358-823394baec9b">KS Events</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560931">KsAddEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562541">KsFilterGenerateEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562597">KsGenerateEvents</a>
 

 

