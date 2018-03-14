---
UID: NF:storport.StorPortNotification
title: StorPortNotification function
author: windows-driver-content
description: The miniport driver uses the StorPortNotification routine to notify the Storport driver of certain events and conditions.
old-location: storage\storportnotification.htm
old-project: storage
ms.assetid: 3f361f50-3ca2-4fb6-828c-27928b50cf55
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortNotification, StorPortNotification routine [Storage Devices], storage.storportnotification, storport/StorPortNotification, storprt_5915c32e-be1b-4786-b391-67be5e61760f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortNotification2, StorPortStatusPending, StorPortTimer
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortNotification
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortNotification function


## -description


The miniport driver uses the <b>StorPortNotification</b> routine to notify the Storport driver of certain events and conditions.

The <b>StorPortNotification</b> routine takes a variable number of parameters depending on the notification type specified.


## -syntax


````
VOID StorPortNotification(
   IN SCSI_NOTIFICATION_TYPE NotificationType,
   IN PVOID                  HwDeviceExtension,
   ...                       arguments
);
````


## -parameters




### -param NotificationType

Specifies the notification type, which can be one of the following values.

<table>
<tr>
<th>Notification type</th>
<th>Description</th>
</tr>
<tr>
<td>
BufferOverrunDetected

</td>
<td>
This notification type has no arguments and gives the miniport driver an opportunity to bugcheck the system if it detects a corruption.

</td>
</tr>
<tr>
<td>
BusChangeDetected

</td>
<td>
Indicates that a target device might have been added or removed from a dynamic bus. To use this notification type, include an optional PathId parameter to indicate the SCSI port or bus where the change was detected.



<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>VOID StorPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ UCHAR                  PathId
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
IoTargetRequestServiceTime

</td>
<td>
Indicates to Storport the amount of time that was required to process a specified request.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>VOID StorPortNotification(
  _In_ SCSI_NOTIFICATION_TYPE NotificationType,
  _In_ PVOID                  HwDeviceExtension,
  _In_ ULONGLONG              Duration,
  _In_ PSCSI_REQUEST_BLOCK    Srb
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
LinkDown

</td>
<td>
Indicates that the link is down and will probably be down for some time. StorPort will pause the adapter in response to this notification.

</td>
</tr>
<tr>
<td>
LinkUp

</td>
<td>
Indicates that the link has been restored. StorPort restarts the adapter so that it can resume operation in response to this notification. Miniport drivers should not send this notification unless the link is down.

</td>
</tr>
<tr>
<td>
QueryTickCount

</td>
<td>
This notification type returns a LARGE_INTEGER that holds the value from <a href="..\wdm\nf-wdm-kequerytickcount.md">KeQueryTickCount</a>. The value returned in TickCount is the count of the interval timer interrupts that have occurred since the system was booted

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>VOID StorPortNotification(
  _In_    SCSI_NOTIFICATION_TYPE NotificationType,
  _In_    PVOID                  HwDeviceExtension,
  _Inout_ PLARGE_INTEGER         TickCount
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
RequestComplete

</td>
<td>
Indicates that the given SRB has finished. After this notification is sent, the port driver owns the request. The Srb parameter represents a pointer to the completed SCSI request block.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>VOID StorPortNotification(
  _In_ SCSI_NOTIFICATION_TYPE NotificationType,
  _In_ PVOID                  HwDeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK    Srb
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
RequestTimerCall

</td>
<td>
Indicates that the miniport driver requires the port driver to call the miniport driver's <a href="..\storport\nc-storport-hw_timer.md">HwStorTimer</a> routine in the requested number of microseconds.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>VOID StorPortNotification(
  _In_ SCSI_NOTIFICATION_TYPE NotificationType,
  _In_ PVOID                  HwDeviceExtension,
  _In_ PHW_TIMER              HwStorTimer,
  _In_ ULONG                  MiniportTimerValue
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
ResetDetected

</td>
<td>
Indicates that the HBA has detected a reset on the bus. After this notification is sent, the miniport driver is still responsible for completing any active requests. The port driver will manage all required bus-reset delays.

</td>
</tr>
<tr>
<td>
WMIEvent

</td>
<td>
Indicates that the miniport driver has detected an event for which one or more WMI data consumers are registered.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>VOID StorPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_     PWNODE_EVENT_ITEM      WMIEvent,
  _In_     UCHAR                  PathId,
  _In_opt_ UCHAR                  TargetId,
  _In_opt_ UCHAR                  Lun
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
WMIReregister

</td>
<td>
Indicates that the miniport driver has changed the data items or the number of instances of a given data block that was previously registered by calling <a href="..\wdm\nf-wdm-iowmiregistrationcontrol.md">IoWMIRegistrationControl</a>.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>VOID StorPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_     UCHAR                  PathId,
  _In_opt_ UCHAR                  TargetId,
  _In_opt_ UCHAR                  Lun
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
</table>
 


### -param HwDeviceExtension

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.


### -param param

TBD




#### - arguments

Specifies the arguments corresponding to the notification type.


## -returns



None.




## -remarks



StorPortNotification is a polymorphic function that handles many different types of requests, making it difficult to annotate in a manner that would cover all possible uses.
Because StorPortNotification returns VOID, the scanning engine should assume the LockHandle was acquired as asked.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567450">StorPortNotification for ResetDetected</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567456">StorPortNotification for WMIReregister</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567447">StorPortNotification for RequestTimerCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567434">StorPortNotification for BufferOverrunDetected</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567437">StorPortNotification for BusChangeDetected</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567439">StorPortNotification for LinkDown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567445">StorPortNotification for QueryTickCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567452">StorPortNotification for WMIEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567446">StorPortNotification for RequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567441">StorPortNotification for LinkUp</a>



<a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>



 

 


