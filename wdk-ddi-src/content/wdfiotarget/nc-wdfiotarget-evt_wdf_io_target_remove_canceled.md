---
UID: NC:wdfiotarget.EVT_WDF_IO_TARGET_REMOVE_CANCELED
title: EVT_WDF_IO_TARGET_REMOVE_CANCELED
author: windows-driver-content
description: A driver's EvtIoTargetRemoveCanceled event callback function performs operations when the removal of a specified remote I/O target is canceled.
old-location: wdf\evtiotargetremovecanceled.htm
old-project: wdf
ms.assetid: 9f275a2c-6f40-461d-bd2c-767b2494ad1c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_5e8c3229-8657-4c26-8bfc-01c8436a8171.xml, EVT_WDF_IO_TARGET_REMOVE_CANCELED, EVT_WDF_IO_TARGET_REMOVE_CANCELED callback, EvtIoTargetRemoveCanceled, EvtIoTargetRemoveCanceled callback function, kmdf.evtiotargetremovecanceled, wdf.evtiotargetremovecanceled, wdfiotarget/EvtIoTargetRemoveCanceled
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	WdfIoTarget.h
api_name:
-	EvtIoTargetRemoveCanceled
product: Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_TARGET_REMOVE_CANCELED callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoTargetRemoveCanceled</i> event callback function performs operations when the removal of a specified remote I/O target is canceled.


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. 


## -returns



None




## -remarks



To register an <i>EvtIoTargetRemoveCanceled</i> callback function, place the callback function's address in the I/O target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 

If the driver's <a href="https://msdn.microsoft.com/cb7c97e5-081e-44fc-a759-9a1ae81de41c">EvtIoTargetQueryRemove</a> callback function called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548589">WdfIoTargetCloseForQueryRemove</a>, the driver's <i>EvtIoTargetRemoveCanceled</i> callback function must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a> to re-enable sending I/O requests to the I/O target. When the driver calls <b>WdfIoTargetOpen</b>, it can specify <b>WdfIoTargetOpenReopen</b> for the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure.

If the driver did not provide an <a href="https://msdn.microsoft.com/cb7c97e5-081e-44fc-a759-9a1ae81de41c">EvtIoTargetQueryRemove</a> callback function, the driver's <i>EvtIoTargetRemoveCanceled</i> callback function can optionally call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a> and specify <b>WdfIoTargetOpenReopen</b>.

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




<a href="https://msdn.microsoft.com/cb7c97e5-081e-44fc-a759-9a1ae81de41c">EvtIoTargetQueryRemove</a>



<a href="https://msdn.microsoft.com/204f101d-770c-4363-9371-0ee76dfa0b2c">EvtIoTargetRemoveComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548589">WdfIoTargetCloseForQueryRemove</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a>
 

 

