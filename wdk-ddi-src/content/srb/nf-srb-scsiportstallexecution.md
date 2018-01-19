---
UID: NF:srb.ScsiPortStallExecution
title: ScsiPortStallExecution function
author: windows-driver-content
description: The ScsiPortStallExecution routine stalls in the miniport driver.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportstallexecution.htm
old-project: storage
ms.assetid: 2b033cfe-9649-4993-b348-6c9af2d0f4bc
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ScsiPortStallExecution
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiPortStallExecution
req.alt-loc: Scsiport.lib,Scsiport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Scsiport.lib
req.dll: 
req.irql: 
req.typenames: *PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# ScsiPortStallExecution function



## -description
The <b>ScsiPortStallExecution</b> routine stalls in the miniport driver.



## -syntax

````
VOID ScsiPortStallExecution(
  _In_ ULONG Delay
);
````


## -parameters

### -param Delay [in]

Specifies the delay interval in microseconds. The given value must be less than a full millisecond.


## -returns
None


## -remarks
<b>ScsiPortStallExecution</b> should be called as seldom as possible and the total stall time in a miniport driver routine must be less than one millisecond. This call ties up a processor, doing no useful work while stalling in the driver.

In general, a miniport driver should call <b>ScsiPortStallExecution</b> only if the driver must wait for a state change on the HBA that cannot cause an interrupt, or if the driver must delay for a very short interval between accesses to the HBA.

If a miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557312">HwScsiInterrupt</a> routine must stall between accesses to the HBA and the total delay time in the ISR might be more than one millisecond, <i>HwScsiInterrupt</i> should call <b>ScsiPortNotification</b> with the <i>NotificationType</i><b>CallEnableInterrupts</b> instead of calling <b>ScsiPortStallExecution</b>. Such a miniport driver has a pair of <i>HwScsi..InterruptsCallback</i> routines to manage its interrupt-driven I/O processing without tying up a processor and degrading the I/O performance of other HBAs that miniport driver might support in the same machine.

A miniport driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff557327">HwScsiTimer</a> routine also can be passed in calls to <b>ScsiPortNotification</b> with a specified interval that is not limited to one millisecond.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557327">HwScsiTimer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557288">HwScsiDisableInterruptsCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557295">HwScsiEnableInterruptsCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557312">HwScsiInterrupt</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortStallExecution routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

