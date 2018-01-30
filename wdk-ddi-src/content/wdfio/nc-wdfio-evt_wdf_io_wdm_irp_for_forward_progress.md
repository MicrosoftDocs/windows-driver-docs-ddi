---
UID: NC:wdfio.EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS
title: EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS
author: windows-driver-content
description: A driver's EvtIoWdmIrpForForwardProgress callback function examines an I/O request packet (IRP) and determines whether to use a reserved request object to process the I/O request or to fail the I/O request.
old-location: wdf\evtiowdmirpforforwardprogress.htm
old-project: wdf
ms.assetid: 71974802-954d-4856-a32b-1dcc45c36ba5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtiowdmirpforforwardprogress, EvtIoWdmIrpForForwardProgress callback function, EvtIoWdmIrpForForwardProgress, EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS, EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS, wdfio/EvtIoWdmIrpForForwardProgress, DFQueueObjectRef_479581ba-4ffd-4aae-b4f0-c246daf38842.xml, kmdf.evtiowdmirpforforwardprogress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfio.h
apiname:
-	EvtIoWdmIrpForForwardProgress
product: Windows
targetos: Windows
req.typenames: "*PWDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO"
req.product: Windows 10 or later.
---

# EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtIoWdmIrpForForwardProgress</i> callback function examines an I/O request packet (IRP) and determines whether to use a reserved request object to process the I/O request or to fail the I/O request.


## -prototype


````
EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS EvtIoWdmIrpForForwardProgress;

WDF_IO_FORWARD_PROGRESS_ACTION EvtIoWdmIrpForForwardProgress(
  _In_ WDFQUEUE Queue,
  _In_ PIRP     Irp
)
{ ... }
````


## -parameters




### -param Queue [in]

A handle to an I/O queue object.


### -param Irp [in]

A pointer to an IRP structure.


## -returns


The <i>EvtIoWdmIrpForForwardProgress</i> callback function must return a <a href="..\wdfio\ne-wdfio-_wdf_io_forward_progress_action.md">WDF_IO_FORWARD_PROGRESS_ACTION</a>-typed value.



## -remarks


A driver can register an <i>EvtIoWdmIrpForForwardProgress</i> callback function when it calls <a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>.

If your driver registers an <i>EvtIoWdmIrpForForwardProgress</i> callback function, the framework calls the function if all of the following conditions exist:
<ul>
<li>
The framework has received a I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>) that the I/O manager is sending to the driver.

</li>
<li>
The framework has attempted to create a request object for the IRP, but the attempt failed.

</li>
<li>
The driver has enabled guaranteed forward progress for the I/O queue that should receive the request object, with the <a href="..\wdfio\ne-wdfio-_wdf_io_forward_progress_reserved_policy.md">policy type</a> set to <b>WdfIoForwardProgressReservedPolicyUseExamine</b>.

</li>
</ul>The framework passes the IRP to the <i>EvtIoWdmIrpForForwardProgress</i> callback function. The callback function must examine the IRP and determine whether the framework should use one of its reserved request objects for the IRP or (if the IRP is not important when the computer's available memory is low) fail the I/O request without delivering it to the driver. The callback function's return value specifies the action that the framework should take.

For more information about the <i>EvtIoWdmIrpForForwardProgress</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.

This callback function can be called at IRQL &lt;= DISPATCH_LEVEL. If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.



## -see-also

<a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_request_resources.md">EvtIoAllocateRequestResources</a>

<a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request.md">EvtIoAllocateResourcesForReservedRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

