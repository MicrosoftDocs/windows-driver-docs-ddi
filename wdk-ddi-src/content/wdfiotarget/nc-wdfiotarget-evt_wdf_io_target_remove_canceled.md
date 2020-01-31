---
UID: NC:wdfiotarget.EVT_WDF_IO_TARGET_REMOVE_CANCELED
title: EVT_WDF_IO_TARGET_REMOVE_CANCELED (wdfiotarget.h)
description: A driver's EvtIoTargetRemoveCanceled event callback function performs operations when the removal of a specified remote I/O target is canceled.
old-location: wdf\evtiotargetremovecanceled.htm
tech.root: wdf
ms.assetid: 9f275a2c-6f40-461d-bd2c-767b2494ad1c
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_5e8c3229-8657-4c26-8bfc-01c8436a8171.xml, EVT_WDF_IO_TARGET_REMOVE_CANCELED, EVT_WDF_IO_TARGET_REMOVE_CANCELED callback, EvtIoTargetRemoveCanceled, EvtIoTargetRemoveCanceled callback function, kmdf.evtiotargetremovecanceled, wdf.evtiotargetremovecanceled, wdfiotarget/EvtIoTargetRemoveCanceled
f1_keywords:
 - "wdfiotarget/EvtIoTargetRemoveCanceled"
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfIoTarget.h
api_name:
- EvtIoTargetRemoveCanceled
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_TARGET_REMOVE_CANCELED callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoTargetRemoveCanceled</i> event callback function performs operations when the removal of a specified remote I/O target is canceled.


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. 


## -remarks



To register an <i>EvtIoTargetRemoveCanceled</i> callback function, place the callback function's address in the I/O target's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 

If the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>, the driver's <i>EvtIoTargetRemoveCanceled</i> callback function must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> to re-enable sending I/O requests to the I/O target. When the driver calls <b>WdfIoTargetOpen</b>, it can specify <b>WdfIoTargetOpenReopen</b> for the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure.

If the driver did not provide an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function, the driver's <i>EvtIoTargetRemoveCanceled</i> callback function can optionally call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> and specify <b>WdfIoTargetOpenReopen</b>.

The optional <i>EvtIoTargetRemoveCanceled</i> callback function should perform any additional operations that might be necessary before the driver resumes sending I/O requests to the I/O target.

For more information about the <i>EvtIoTargetRemoveCanceled</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>.


#### Examples

To define an <i>EvtIoTargetRemoveCanceled</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoTargetRemoveCanceled</i> callback function that is named <i>MyIoTargetRemoveCanceled</i>, use the <b>EVT_WDF_IO_TARGET_REMOVE_CANCELED</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_TARGET_REMOVE_CANCELED  MyIoTargetRemoveCanceled;</pre>
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
VOID
 MyIoTargetRemoveCanceled (
    WDFIOTARGET  IoTarget
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_TARGET_REMOVE_CANCELED</b> function type is defined in the WdfIoTarget.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_TARGET_REMOVE_CANCELED</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_complete">EvtIoTargetRemoveComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>
 

 

