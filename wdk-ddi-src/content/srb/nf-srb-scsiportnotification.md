---
UID: NF:srb.ScsiPortNotification
title: ScsiPortNotification function (srb.h)
description: The ScsiPortNotification routine informs the operating system-specific port driver of certain events, such as when a miniport driver completes a request or is ready to start another SRB, as well as when the HBA indicates certain SCSI error conditions that occurred during an operation.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportnotification.htm
tech.root: storage
ms.assetid: 27da3881-4c47-492c-868e-ce72210e9d6f
ms.date: 03/29/2018
keywords: ["ScsiPortNotification function"]
ms.keywords: ScsiPortNotification, ScsiPortNotification routine [Storage Devices], scsiprt_0e410e4a-e7bb-448b-9d4d-c2a5db63fe02.xml, srb/ScsiPortNotification, storage.scsiportnotification
f1_keywords:
 - "srb/ScsiPortNotification"
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
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
req.lib: Scsiport.lib; Storport.lib
req.dll: 
req.irql: (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- scsiport.lib
- scsiport.dll
- storport.lib
- storport.dll
api_name:
- ScsiPortNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortNotification function


## -description


The <b>ScsiPortNotification</b> routine informs the operating system-specific port driver of certain events, such as when a miniport driver completes a request or is ready to start another SRB, as well as when the HBA indicates certain SCSI error conditions that occurred during an operation.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param NotificationType

Specifies the type of notification, which can be one of the following.

<table>
<tr>
<th>Notification Type</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>RequestComplete</b>

</td>
<td>
Indicates that the given <i>Srb</i> has finished. If this value is set, <b>ScsiPortNotification</b> requires one additional parameter: the address of the SRB. After this notification, the operating system-specific port driver owns the request. The miniport driver must not access the <i>Srb</i>, and it must not pass the <i>Srb</i> to another routine (such as <b>ScsiPortLogError</b>).

Syntax: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ PSCSI_REQUEST_BLOCK    Srb
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
<b>NextRequest</b>

</td>
<td>
Indicates the miniport driver is ready for another request to a target that is not currently busy. This notification should be sent by the miniport driver as soon as the driver is ready for another request. Usually, this notification is sent from the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557323(v=vs.85)">HwScsiStartIo</a> routine but, sometimes, from the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557312(v=vs.85)">HwScsiInterrupt</a> (or <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557295(v=vs.85)">HwScsiEnableInterruptsCallback</a>) routine.

</td>
</tr>
<tr>
<td>
<b>NextLuRequest</b>

</td>
<td>
Indicates that the HBA is ready for another request for the specified logical unit. If this value is set, <b>ScsiPortNotification</b> requires three additional parameters: (1) the path ID, (2) the target ID, and (3) the logical unit number. This value should be used only if the HBA can queue multiple requests and support auto-request sense or tagged queuing. 

Syntax:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_                        PathId,
  _In_opt_                        TargetId,
  _In_opt_                        Lun
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
<b>ResetDetected</b>

</td>
<td>
Indicates that the HBA has detected a reset on the SCSI bus. After this notification, the miniport driver is still responsible for completing any active requests. The SCSI port driver will manage all required bus-reset delays.

</td>
</tr>
<tr>
<td>
<b>CallEnableInterrupts</b>

</td>
<td>
Indicates that the miniport driver requires the operating system-specific port driver to call the miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557295(v=vs.85)">HwScsiEnableInterruptsCallback</a> routine. If this value is set, <b>ScsiPortNotification</b> requires an additional parameter: the entry point for the <i>HwScsiEnableInterruptsCallback</i>. The miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557312(v=vs.85)">HwScsiInterrupt</a> routine makes this call,<i> after </i>disabling interrupts on the HBA, to defer some interrupt-driven I/O processing if the HBA requires polling or stalling in the ISR. While the callback runs, system interrupts remain enabled but the miniport driver's <i>HwScsiInterrupt</i> routine will not be called. The <i>HwScsiEnableInterruptsCallback</i> is responsible for completing the deferred I/O processing and for calling <b>ScsiPortNotification</b> again with <b>CallDisableInterrupts</b> and the miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557288(v=vs.85)">HwScsiDisableInterruptsCallback</a> entry point.

Syntax:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ PHW_INTERRUPT          HwScsiXxxInterruptsCallback
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
<b>CallDisableInterrupts</b>

</td>
<td>
Indicates that the miniport driver requires the operating system-specific port driver to call the miniport driver's <i>HwScsiDisableInterruptsCallback</i> routine. If this value is set, <b>ScsiPortNotification</b> requires an additional parameter: the entry point for the <i>HwScsiDisableInterruptsCallback</i>. While this callback runs, it cannot be preempted by an interrupt except from a device with a higher priority interrupt than the HBA. In this callback, the miniport driver reenables interrupts on the HBA.

Syntax:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ PHW_INTERRUPT          HwScsiXxxInterruptsCallback
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
<b>RequestTimerCall</b>

</td>
<td>
Indicates that the miniport driver requires the operating system-specific port driver to call the miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557327(v=vs.85)">HwScsiTimer</a> routine in the requested number of microseconds. If this value is set, <b>ScsiPortNotification</b> requires two additional parameters: (1) the entry point for the miniport driver's <i>HwScsiTimer</i> routine, and (2) a <i>MiniportTimerValue</i> interval, in microseconds. Note that the resolution of the system timer is approximately 10 milliseconds.

Syntax:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ PHW_TIMER              HwScsiTimer,
  _In_opt_ ULONG                  MiniportTimerValue
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
<b>BusChangeDetected</b>

</td>
<td>
Indicates that a target device might have been added or removed from a dynamic bus. If this value is set, <b>ScsiPortNotification</b> requires an additional parameter: the path ID of the bus on which the change was detected. After this notification, the port driver reenumerates the bus by issuing INQUIRY commands. Bus enumeration is time-consuming and ties up the bus, so a miniport driver should not send this notification unnecessarily 

Syntax:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
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
<b>WMIEvent</b>

</td>
<td>
Indicates that the miniport driver has detected an event for which one or more WMI data consumers is registered. If this value is set, <b>ScsiPortNotification</b> requires at least three additional arguments: (1) a pointer to a WMI event structure, (2) the size of the event structure, and (3) the path ID of the target device if the event originated from a device, or 0Xff if the event originated from the adapter. If (3) is a path ID, <b>ScsiPortNotification</b> requires two additional arguments: (4) the target ID, and (5) the logical unit number (LUN) of the target device. 

Syntax for PathId != 0xFF

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ PVOID                  WMIEvent,
  _In_opt_ UCHAR                  PathId,
  _In_opt_ UCHAR                  TargetId,
  _In_opt_ UCHAR                  Lun
);</pre>
</td>
</tr>
</table></span></div>
Syntax for PathId = 0xFF

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ PVOID                  WMIEvent,
  _In_opt_ UCHAR                  PathId
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
<tr>
<td>
<b>WMIReregister</b>

</td>
<td>
Indicates that the miniport driver has changed the data items or the number of instances of a given data block previously registered by calling <b>IoWMIRegistrationControl</b>. If <b>WMIReregister</b> is set, <b>ScsiPortNotification</b> requires at least two additional arguments: (1) the path ID of the target device to reregister that device, or 0xFF to reregister the adapter. If (1) is a path ID, <b>ScsiPortNotification</b> requires two additional arguments: (2) the target ID, and (3) the logical unit number (LUN) of the target device. 

Syntax for PathId != 0xFF

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ UCHAR                  PathId,
  _In_opt_ UCHAR                  TargetId,
  _In_opt_ UCHAR                  Lun
);</pre>
</td>
</tr>
</table></span></div>
Syntax for PathId = 0xFF

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID ScsiPortNotification(
  _In_     SCSI_NOTIFICATION_TYPE NotificationType,
  _In_     PVOID                  HwDeviceExtension,
  _In_opt_ UCHAR                  PathId
);</pre>
</td>
</tr>
</table></span></div>
</td>
</tr>
</table>
 


### -param HwDeviceExtension

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param param

TBD




## -returns



None




## -remarks



The <b>ScsiPortNotification</b> routine has a different set of optional parameters associated with each <i>NotificationType</i>. For a description of the optional parameters associated a particular <i>NotificationType</i>, see the reference page associated with that <i>NotificationType</i>. The following reference pages provide this information:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = RequestComplete)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = NextRequest)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = NextLuRequest)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = ResetDetected)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = CallEnableInterrupts or CallDisableInterrupts)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = RequestTimerCall)</a><b>)</b>


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = BusChangeDetected)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = WMIEvent, PathId != 0xFF)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = WMIEvent, PathId = 0xFF)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = WMIReregister, PathId != 0xFF)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification (NotificationType = WMIReregister, PathId = 0xFF)</a>


Every miniport driver must call <b>ScsiPortNotification</b> twice for each call to the miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557323(v=vs.85)">HwScsiStartIo</a> routine with an SRB that the miniport driver completes successfully. First, the miniport driver calls <b>ScsiPortNotification</b> with the <i>NotificationType</i><b>NextRequest</b> or with <b>NextLuRequest</b> if the miniport driver supports tagged queuing or multiple requests per LU. Then, the miniport driver calls <b>ScsiPortNotification</b> with the <i>NotificationType</i><b>RequestComplete</b> and the request that it has just satisfied.

A miniport driver's <i>HwScsiInterrupt</i> routine is most likely to call <b>ScsiPortNotification</b> with the <i>NotificationType</i><b>ResetDetected</b>.

If an HBA requires the miniport driver to use more than a millisecond processing interrupt-driven I/O operations, its <i>HwScsiInterrupt</i> routine should disable interrupts on the HBA and call <b>ScsiPortNotification</b> with <b>CallEnableInterrupts</b> and a driver-supplied <i>HwScsiEnableInterruptsCallback</i> routine. This routine, in turn, calls <b>ScsiPortNotification</b> with <b>CallDisableInterrupts</b> and the corresponding driver-supplied <i>HwScsiDisableInterruptsCallback</i>.

A miniport driver that is registered as a WMI data provider can call <b>ScsiPortNotification</b> with <b>WMIEvent</b> to post an event for which it has previously received an enable request. The port driver queues the event in the interrupt data area of the miniport driver's device extension for later processing at a lower IRQL. Because only a limited number of events can be queued at one time, the miniport driver should use <b>WMIEvent</b> to signal exceptional rather than routine conditions, and it should give the port driver time to get back to DISPATCH_LEVEL between postings, to prevent events from being lost. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557288(v=vs.85)">HwScsiDisableInterruptsCallback</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557295(v=vs.85)">HwScsiEnableInterruptsCallback</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557327(v=vs.85)">HwScsiTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiregistrationcontrol">IoWMIRegistrationControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportcompleterequest">ScsiPortCompleteRequest</a>
 

 

