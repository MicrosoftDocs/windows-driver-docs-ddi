---
UID: NF:wdm.IoReportTargetDeviceChange
title: IoReportTargetDeviceChange function
author: windows-driver-content
description: The IoReportTargetDeviceChange routine notifies the PnP manager that a custom event has occurred on a device.
old-location: kernel\ioreporttargetdevicechange.htm
old-project: kernel
ms.assetid: b0107cb1-4828-4ede-813e-934b929c9874
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoReportTargetDeviceChange, IoReportTargetDeviceChange routine [Kernel-Mode Driver Architecture], k104_489fe1b0-1d73-4ed6-99ab-ae8f4bee52d1.xml, kernel.ioreporttargetdevicechange, wdm/IoReportTargetDeviceChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoReportTargetDeviceChange
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoReportTargetDeviceChange function


## -description


The <b>IoReportTargetDeviceChange</b> routine notifies the PnP manager that a custom event has occurred on a device.


## -parameters




### -param PhysicalDeviceObject [in]

Pointer to the PDO of the device being reported.


### -param NotificationStructure [in]

Pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff564596">TARGET_DEVICE_CUSTOM_NOTIFICATION</a> structure describing the custom event. The PnP manager sends this structure to drivers that registered for notification of the event.

<i>NotificationStructure</i>.<b>FileObject</b> must be <b>NULL</b>. <i>NotificationStructure</i>.<b>Event</b> must contain the custom GUID for the event. The other fields of the <i>NotificationStructure</i> must be filled in as appropriate for the custom event.

The PnP manager fills in the <i>NotificationStructure</i>.<b>FileObject</b> field when it sends notifications to registrants.


## -returns



<b>IoReportTargetDeviceChange</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The caller specified a system PnP event, such as GUID_TARGET_DEVICE_QUERY_REMOVE. This routine is only for custom events.

</td>
</tr>
</table>
 




## -remarks



After <b>IoReportTargetDeviceChange</b> notifies the PnP manager that a custom event has occurred on a device, the PnP manager sends notification of the event to drivers that registered for notification on the device. Do not use this routine to report system PnP events, such as GUID_TARGET_DEVICE_REMOVE_COMPLETE.

A driver that defines a custom device event calls <b>IoReportTargetDeviceChange</b> to inform the PnP manager that the custom event has occurred. Custom notification can be used for events like a volume label change.

A driver should call the asynchronous form of this routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549634">IoReportTargetDeviceChangeAsynchronous</a>, instead of this routine, to prevent deadlocks.

Certain kernel-mode components can call this synchronous routine. For example, a file system can call <b>IoReportTargetDeviceChange</b> to report a "get off the volume" custom event when a component tries to open the volume for exclusive access. Clients that register for notification on file system volumes are careful to not request an exclusive open in a PnP notification callback routine.

The custom notification structure contains a driver-defined event with its own GUID. Driver writers can generate GUIDs with Uuidgen.exe or Guidgen.exe (which are included in the Microsoft Windows SDK).

Callers of <b>IoReportTargetDeviceChange</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread. To report a target device change from IRQL &gt; PASSIVE_LEVEL, call <b>IoReportTargetDeviceChangeAsynchronous</b>.

<b>IoReportTargetDeviceChange</b> is not supported on Windows 98/Me; it returns STATUS_NOT_IMPLEMENTED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549634">IoReportTargetDeviceChangeAsynchronous</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564596">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoReportTargetDeviceChange routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

