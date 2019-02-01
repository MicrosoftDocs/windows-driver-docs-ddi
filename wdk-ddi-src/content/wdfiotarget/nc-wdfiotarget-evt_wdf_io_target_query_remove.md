---
UID: NC:wdfiotarget.EVT_WDF_IO_TARGET_QUERY_REMOVE
title: EVT_WDF_IO_TARGET_QUERY_REMOVE (wdfiotarget.h)
description: A driver's EvtIoTargetQueryRemove event callback function indicates whether the framework can safely remove a specified remote I/O target's device.
old-location: wdf\evtiotargetqueryremove.htm
tech.root: wdf
ms.assetid: cb7c97e5-081e-44fc-a759-9a1ae81de41c
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_9a471005-a4c8-4918-bc4c-4147bd6018f0.xml, EVT_WDF_IO_TARGET_QUERY_REMOVE, EVT_WDF_IO_TARGET_QUERY_REMOVE callback, EvtIoTargetQueryRemove, EvtIoTargetQueryRemove callback function, kmdf.evtiotargetqueryremove, wdf.evtiotargetqueryremove, wdfiotarget/EvtIoTargetQueryRemove
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
-	EvtIoTargetQueryRemove
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_TARGET_QUERY_REMOVE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoTargetQueryRemove</i> event callback function indicates whether the framework can safely remove a specified remote I/O target's device. 


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. 


## -returns



The<i>EvtIoTargetQueryRemove</i> callback function must return STATUS_SUCCESS if the driver determines that the framework can safely remove the specified I/O target's device. Otherwise, this callback function must return STATUS_UNSUCCESSFUL.




## -remarks



If a driver's <i>EvtIoTargetQueryRemove</i> callback function returns STATUS_SUCCESS, the system allows the I/O target's device to be removed, unless another driver returns STATUS_UNSUCCESSFUL.

To register an <i>EvtIoTargetQueryRemove</i> callback function, place the callback function's address in the I/O target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure. The <i>EvtIoTargetQueryRemove</i> callback function is optional. Not supplying this callback function is equivalent to returning STATUS_SUCCESS.

The <i>EvtIoTargetQueryRemove</i> callback function must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548589">WdfIoTargetCloseForQueryRemove</a>, if the driver determines that the PnP manager can safely remove the target device.

The callback function must disable the driver's ability to send additional I/O requests to the I/O target.

For more information about the <i>EvtIoTargetQueryRemove</i> callback function, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>.


#### Examples

To define an <i>EvtIoTargetQueryRemove</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoTargetQueryRemove</i> callback function that is named <i>MyIoTargetQueryRemove</i>, use the <b>EVT_WDF_IO_TARGET_QUERY_REMOVE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_TARGET_QUERY_REMOVE  MyIoTargetQueryRemove;</pre>
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
 MyIoTargetQueryRemove (
    WDFIOTARGET  IoTarget
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_TARGET_QUERY_REMOVE</b> function type is defined in the WdfIoTarget.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_TARGET_QUERY_REMOVE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/9f275a2c-6f40-461d-bd2c-767b2494ad1c">EvtIoTargetRemoveCanceled</a>



<a href="https://msdn.microsoft.com/204f101d-770c-4363-9371-0ee76dfa0b2c">EvtIoTargetRemoveComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548589">WdfIoTargetCloseForQueryRemove</a>
 

 

