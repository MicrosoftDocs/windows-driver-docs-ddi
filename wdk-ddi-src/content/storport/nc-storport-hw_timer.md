---
UID: NC:storport.HW_TIMER
title: HW_TIMER
author: windows-driver-content
description: The HwStorTimer routine is called after the interval that is specified when the miniport driver called StorPortNotification with the RequestTimerCall NotificationType value.
old-location: storage\hwstortimer.htm
old-project: storage
ms.assetid: 61aced1b-9f8a-454a-901c-561ec6179873
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwstortimer, HwStorTimer routine [Storage Devices], HwStorTimer, HW_TIMER, HW_TIMER, storport/HwStorTimer, stormini_6127daf5-8672-4bf4-9241-b67bed14b8f8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
-	Storport.h
apiname:
-	HwStorTimer
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# HW_TIMER callback


## -description


The <b>HwStorTimer</b> routine is called after the interval that is specified when the miniport driver called <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> with the <b>RequestTimerCall</b><i> NotificationType</i> value.


## -prototype


````
HW_TIMER HwStorTimer;

VOID HwStorTimer(
   IN PVOID DeviceExtension
)
{ ... }
````


## -parameters




### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.


## -returns


None



## -remarks


The name <b>HwStorTimer</b> is only a placeholder. The actual prototype of this routine is defined in <i>Srb.h</i> as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_TIMER (
  _In_ PVOID  DeviceExtension
  );</pre>
</td>
</tr>
</table></span></div>If the miniport opts into multi-channel support, the StartIo spin lock is still taken. However, if the miniport has requested multiple channel support via PERF_CONFIGURATION_DATA, the StartIo spin lock is not taken or checked before the call to <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a> in the miniport.  This means that the <i>HwStorStartIo</i> callback  is not synchronized with the callback to the <i>HwStorTimer</i> routine when multi-channel support is used.  The miniport must do this on its own by using a compiler interlocked intrinsic, for example using <a href="..\wdm\nf-wdm-interlockedcompareexchange.md">InterlockedCompareExchange</a>. 

A <b>HwStorTimer</b> routine is optional.



## -see-also

<a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_TIMER routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

