---
UID: NC:wdfiotarget.EVT_WDF_IO_TARGET_REMOVE_CANCELED
title: EVT_WDF_IO_TARGET_REMOVE_CANCELED
author: windows-driver-content
description: A driver's EvtIoTargetRemoveCanceled event callback function performs operations when the removal of a specified remote I/O target is canceled.
old-location: wdf\evtiotargetremovecanceled.htm
old-project: wdf
ms.assetid: 9f275a2c-6f40-461d-bd2c-767b2494ad1c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFIOTargetRef_5e8c3229-8657-4c26-8bfc-01c8436a8171.xml, EVT_WDF_IO_TARGET_REMOVE_CANCELED, EvtIoTargetRemoveCanceled, EvtIoTargetRemoveCanceled callback function, kmdf.evtiotargetremovecanceled, wdf.evtiotargetremovecanceled, wdfiotarget/EvtIoTargetRemoveCanceled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfIoTarget.h
apiname:
-	EvtIoTargetRemoveCanceled
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, *PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY
req.product: Windows 10 or later.
---

# EVT_WDF_IO_TARGET_REMOVE_CANCELED callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoTargetRemoveCanceled</i> event callback function performs operations when the removal of a specified remote I/O target is canceled.


## -prototype


````
EVT_WDF_IO_TARGET_REMOVE_CANCELED EvtIoTargetRemoveCanceled;

VOID EvtIoTargetRemoveCanceled(
  _In_ WDFIOTARGET IoTarget
)
{ ... }
````


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. 


## -returns



None




## -remarks



To register an <i>EvtIoTargetRemoveCanceled</i> callback function, place the callback function's address in the I/O target's <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 

If the driver's <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function called <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>, the driver's <i>EvtIoTargetRemoveCanceled</i> callback function must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> to re-enable sending I/O requests to the I/O target. When the driver calls <b>WdfIoTargetOpen</b>, it can specify <b>WdfIoTargetOpenReopen</b> for the <b>Type</b> member of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure.

If the driver did not provide an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function, the driver's <i>EvtIoTargetRemoveCanceled</i> callback function can optionally call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> and specify <b>WdfIoTargetOpenReopen</b>.

The optional <i>EvtIoTargetRemoveCanceled</i> callback function should perform any additional operations that might be necessary before the driver resumes sending I/O requests to the I/O target.

For more information about the <i>EvtIoTargetRemoveCanceled</i> callback function, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>.


#### Examples

To define an <i>EvtIoTargetRemoveCanceled</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

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
The <b>EVT_WDF_IO_TARGET_REMOVE_CANCELED</b> function type is defined in the WdfIoTarget.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_TARGET_REMOVE_CANCELED</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>



<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_complete.md">EvtIoTargetRemoveComplete</a>



<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_TARGET_REMOVE_CANCELED callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

