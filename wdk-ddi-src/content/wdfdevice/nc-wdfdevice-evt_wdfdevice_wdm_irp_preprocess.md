---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_IRP_PREPROCESS
title: EVT_WDFDEVICE_WDM_IRP_PREPROCESS (wdfdevice.h)
description: A driver's EvtDeviceWdmIrpPreprocess event callback function receives an IRP before the framework processes the IRP.
old-location: wdf\evtdevicewdmirppreprocess.htm
tech.root: wdf
ms.assetid: aff9cb60-d61b-47a8-aae4-6ffd2a1b7a9a
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_7329adf6-5814-40cb-ac9b-a7fb67b5f05c.xml, EVT_WDFDEVICE_WDM_IRP_PREPROCESS, EVT_WDFDEVICE_WDM_IRP_PREPROCESS callback, EvtDeviceWdmIrpPreprocess, EvtDeviceWdmIrpPreprocess callback function, kmdf.evtdevicewdmirppreprocess, wdf.evtdevicewdmirppreprocess, wdfdevice/EvtDeviceWdmIrpPreprocess
ms.topic: callback
f1_keywords:
 - "wdfdevice/EvtDeviceWdmIrpPreprocess"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceWdmIrpPreprocess
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDFDEVICE_WDM_IRP_PREPROCESS callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceWdmIrpPreprocess</i> event callback function receives an IRP before the framework processes the IRP.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Irp [in, out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_irp">IRP</a> structure.


## -returns



The <i>EvtDeviceWdmIrpPreprocess</i> callback function must:


<ul>
<li>Set the <b>IoStatus.Status</b> member of the IRP to STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(status) equals <b>TRUE</b>, and return the same value (after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>), if the callback function successfully completes the received IRP.</li>
<li>Set the <b>IoStatus.Status</b> member of the IRP to a status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(status) equals <b>FALSE</b>, and return the same value (after calling IoCompleteRequest), if the callback function detects an error. </li>
<li>Return STATUS_PENDING, if the callback function calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iomarkirppending">IoMarkIrpPending</a>. 
</li>
<li>Return the value that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a> method returns, if the callback function calls that method. 
</li>
</ul>





## -remarks



To register an <i>EvtDeviceWdmIrpPreprocess</i> callback function, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitassignwdmirppreprocesscallback">WdfDeviceInitAssignWdmIrpPreprocessCallback</a>. 

Your driver can use an <i>EvtDeviceWdmIrpPreprocess</i> callback function to do any, or all, of the following:

<ul>
<li>
 Handle an IRP that the framework does not support, by following the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-irps">WDM rules for handling IRPs</a>. 

</li>
<li>
 Preprocess an IRP before the framework handles it. 

</li>
<li>
 Set a completion routine so that the driver can postprocess an IRP after the framework handles it. 

</li>
</ul>
For more information about how to implement an <i>EvtDeviceWdmIrpPreprocess</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-wdm-irps-outside-of-the-framework">Handling WDM IRPs Outside of the Framework</a>.

If you want the framework to subsequently handle the IRP as it would if the <i>EvtDeviceWdmIrpPreprocess</i> callback function had not been called, the callback function must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a> to return the IRP to the framework.

If your driver registers an <i>EvtDeviceWdmIrpPreprocess</i> callback function, the framework adds an additional <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/i-o-stack-locations">I/O stack location</a> to IRPs that the callback function receives. The additional I/O stack location allows the callback function to set an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a>.

The <i>EvtDeviceWdmIrpPreprocess</i> callback function is called at the IRQL of the calling thread. The IRQL is determined by the type of IRP that the framework is passing to <i>EvtDeviceWdmIrpPreprocess</i>. For example, if the PnP manager sends <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations">IRP_MN_QUERY_DEVICE_RELATIONS</a> at IRQL = PASSIVE_LEVEL, the framework calls <i>EvtDeviceWdmIrpPreprocess</i> at IRQL = PASSIVE_LEVEL.


#### Examples

To define an <i>EvtDeviceWdmIrpPreprocess</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

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
The <b>EVT_WDFDEVICE_WDM_IRP_PREPROCESS</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDFDEVICE_WDM_IRP_PREPROCESS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitassignwdmirppreprocesscallback">WdfDeviceInitAssignWdmIrpPreprocessCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a>
 

 

