---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_IRP_PREPROCESS
title: EVT_WDFDEVICE_WDM_IRP_PREPROCESS
author: windows-driver-content
description: A driver's EvtDeviceWdmIrpPreprocess event callback function receives an IRP before the framework processes the IRP.
old-location: wdf\evtdevicewdmirppreprocess.htm
old-project: wdf
ms.assetid: aff9cb60-d61b-47a8-aae4-6ffd2a1b7a9a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectGeneralRef_7329adf6-5814-40cb-ac9b-a7fb67b5f05c.xml, EVT_WDFDEVICE_WDM_IRP_PREPROCESS, EvtDeviceWdmIrpPreprocess, EvtDeviceWdmIrpPreprocess callback function, kmdf.evtdevicewdmirppreprocess, wdf.evtdevicewdmirppreprocess, wdfdevice/EvtDeviceWdmIrpPreprocess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceWdmIrpPreprocess
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDFDEVICE_WDM_IRP_PREPROCESS callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDeviceWdmIrpPreprocess</i> event callback function receives an IRP before the framework processes the IRP.


## -prototype


````
EVT_WDFDEVICE_WDM_IRP_PREPROCESS EvtDeviceWdmIrpPreprocess;

NTSTATUS EvtDeviceWdmIrpPreprocess(
  _In_    WDFDEVICE Device,
  _Inout_ PIRP      Irp
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Irp [in, out]

A pointer to an <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure.


## -returns



The <i>EvtDeviceWdmIrpPreprocess</i> callback function must:


<ul>
<li>Set the <b>IoStatus.Status</b> member of the IRP to STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(status) equals <b>TRUE</b>, and return the same value (after calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>), if the callback function successfully completes the received IRP.</li>
<li>Set the <b>IoStatus.Status</b> member of the IRP to a status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(status) equals <b>FALSE</b>, and return the same value (after calling IoCompleteRequest), if the callback function detects an error. </li>
<li>Return STATUS_PENDING, if the callback function calls <a href="..\wdm\nf-wdm-iomarkirppending.md">IoMarkIrpPending</a>. 
</li>
<li>Return the value that the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp.md">WdfDeviceWdmDispatchPreprocessedIrp</a> method returns, if the callback function calls that method. 
</li>
</ul>





## -remarks



To register an <i>EvtDeviceWdmIrpPreprocess</i> callback function, your driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignwdmirppreprocesscallback.md">WdfDeviceInitAssignWdmIrpPreprocessCallback</a>. 

Your driver can use an <i>EvtDeviceWdmIrpPreprocess</i> callback function to do any, or all, of the following:

<ul>
<li>
 Handle an IRP that the framework does not support, by following the <a href="https://msdn.microsoft.com/5fb6d2b9-17ee-4e76-95e9-dd5a7d1e79de">WDM rules for handling IRPs</a>. 

</li>
<li>
 Preprocess an IRP before the framework handles it. 

</li>
<li>
 Set a completion routine so that the driver can postprocess an IRP after the framework handles it. 

</li>
</ul>
For more information about how to implement an <i>EvtDeviceWdmIrpPreprocess</i> callback function, see <a href="https://msdn.microsoft.com/43e1df0c-c0d1-4d41-87de-9f8f5831fb19">Handling WDM IRPs Outside of the Framework</a>.

If you want the framework to subsequently handle the IRP as it would if the <i>EvtDeviceWdmIrpPreprocess</i> callback function had not been called, the callback function must call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp.md">WdfDeviceWdmDispatchPreprocessedIrp</a> to return the IRP to the framework.

If your driver registers an <i>EvtDeviceWdmIrpPreprocess</i> callback function, the framework adds an additional <a href="https://msdn.microsoft.com/62c8ee00-c7cb-4aa1-90ab-b8bedbd818ee">I/O stack location</a> to IRPs that the callback function receives. The additional I/O stack location allows the callback function to set an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp.md">WdfDeviceWdmDispatchPreprocessedIrp</a>.

The <i>EvtDeviceWdmIrpPreprocess</i> callback function is called at the IRQL of the calling thread. The IRQL is determined by the type of IRP that the framework is passing to <i>EvtDeviceWdmIrpPreprocess</i>. For example, if the PnP manager sends <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> at IRQL = PASSIVE_LEVEL, the framework calls <i>EvtDeviceWdmIrpPreprocess</i> at IRQL = PASSIVE_LEVEL.


#### Examples

To define an <i>EvtDeviceWdmIrpPreprocess</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceWdmIrpPreprocess</i> callback function that is named <i>MyDeviceWdmIrpPreprocess</i>, use the <b>EVT_WDFDEVICE_WDM_IRP_PREPROCESS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDFDEVICE_WDM_IRP_PREPROCESS  MyDeviceWdmIrpPreprocess;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyDeviceWdmIrpPreprocess (
    WDFDEVICE  Device,
    PIRP  Irp
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDFDEVICE_WDM_IRP_PREPROCESS</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDFDEVICE_WDM_IRP_PREPROCESS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignwdmirppreprocesscallback.md">WdfDeviceInitAssignWdmIrpPreprocessCallback</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp.md">WdfDeviceWdmDispatchPreprocessedIrp</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDFDEVICE_WDM_IRP_PREPROCESS callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

