---
UID: NC:wdm.REQUEST_POWER_COMPLETE
title: REQUEST_POWER_COMPLETE
author: windows-driver-content
description: The PowerCompletion callback routine completes the processing of a power IRP.
old-location: kernel\powercompletion.htm
old-project: kernel
ms.assetid: 2272790e-324a-4bd4-86ed-b76305a2940b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.powercompletion, PowerCompletion routine [Kernel-Mode Driver Architecture], PowerCompletion, REQUEST_POWER_COMPLETE, REQUEST_POWER_COMPLETE, wdm/PowerCompletion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 2000 and later versions of Windows.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL (see Remarks section).
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	PowerCompletion
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# REQUEST_POWER_COMPLETE callback


## -description


The <i>PowerCompletion</i> callback routine completes the processing of a power IRP.


## -prototype


````
REQUEST_POWER_COMPLETE PowerCompletion;

VOID PowerCompletion(
  _In_     PDEVICE_OBJECT   DeviceObject,
  _In_     UCHAR            MinorFunction,
  _In_     POWER_STATE      PowerState,
  _In_opt_ PVOID            Context,
  _In_     PIO_STATUS_BLOCK IoStatus
)
{ ... }
````


## -parameters




#### - DeviceObject [in]

A pointer to the target <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> for the completed power IRP.


#### - MinorFunction [in]

Specifies the minor function code in the power IRP. For more information, see the list of supported <b>IRP_MN_<i>XXX</i></b> codes in the Remarks section.


#### - PowerState [in]

Specifies the <a href="https://msdn.microsoft.com/2229f34c-9b88-4e3e-802e-f7be2c7ef168">device power state</a> or <a href="https://msdn.microsoft.com/bb30bc89-d1f2-4cb3-bcfb-fb76c69dba27">system power state</a> that was passed to the <a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a> routine.


#### - Context [in, optional]

A pointer to the context that was passed to <b>PoRequestPowerIrp</b>.


#### - IoStatus [in]

A pointer to the <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure for the completed IRP.


## -returns


None



## -remarks


A driver that sends a power IRP might need to perform additional tasks after all other drivers have completed the IRP. If so, the sending driver should register a <i>PowerCompletion</i> callback routine during the call to the <a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a> routine that allocates the IRP.

A driver's <i>PowerCompletion</i> callback routine is used only for <a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a> IRPs that have minor IRP codes of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563731">Sending IRP_MN_QUERY_POWER or IRP_MN_SET_POWER for Device Power States</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff565599">Wait/Wake Callback Routines</a>.

The I/O manager calls the sending driver's <i>PowerCompletion</i> routine only after the I/O manager has called all the <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routines that were set by other drivers as they passed the IRP down the stack. The <i>PowerCompletion</i> routine performs any additional tasks that the sender of the IRP requires after all other drivers have completed the IRP. The <i>PowerCompletion</i> routine should not free the IRP—the power manager does that.

In Windows 2000 and later versions of Windows, the <i>PowerCompletion</i> routine is called at IRQL = PASSIVE_LEVEL or IRQL = DISPATCH_LEVEL. In Windows 98/Me, the <i>PowerCompletion</i> routine is always called at IRQL = PASSIVE_LEVEL, and drivers must complete IRPs at IRQL = PASSIVE_LEVEL.




## -see-also

<a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a>

<a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a>

<a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PowerCompletion routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

