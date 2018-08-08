---
UID: NC:wdfworkitem.EVT_WDF_WORKITEM
title: EVT_WDF_WORKITEM
author: windows-driver-content
description: A driver's EvtWorkItem event callback function performs the work that is associated with a specified work item.
old-location: wdf\evtworkitem.htm
tech.root: wdf
ms.assetid: 2a2811de-9024-40a8-b8af-b61ca4100218
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWorkItemObjectRef_e799d95c-bbde-402a-8ba6-6e03256772ff.xml, EVT_WDF_WORKITEM, EVT_WDF_WORKITEM callback, EvtWorkItem, EvtWorkItem callback function, kmdf.evtworkitem, wdf.evtworkitem, wdfworkitem/EvtWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfworkitem.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfworkitem.h
api_name:
-	EvtWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_WORKITEM callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtWorkItem</i> event callback function performs the work that is associated with a specified work item.


## -parameters




### -param WorkItem [in]

A handle to a framework work-item object.


## -returns



None




## -remarks



Typically, a driver's <i>EvtWorkItem</i> callback function performs tasks that are specified by information that the driver stored in the context memory of a work-item object. 

To register an <i>EvtWorkItem</i> callback function, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>.

After the <i>EvtWorkItem</i> callback function has performed the specified tasks, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a>, unless the driver reuses work items. 

For more information about work items, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.

The <i>EvtWorkItem</i> callback function runs at IRQL = PASSIVE_LEVEL in the context of a system worker thread.


#### Examples

To define an <i>EvtWorkItem</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtWorkItem</i> callback function that is named <i>MyWorkItem</i>, use the <b>EVT_WDF_WORKITEM</b> type as shown in this code example:

<div class="code"></div>
To define an <i>EvtWorkItem</i> callback function that is named <b>MyWorkItem</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_WORKITEM  MyWorkItem;</pre>
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
 MyWorkItem (
    WDFWORKITEM  WorkItem
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_WORKITEM</b> function type is defined in the Wdfworkitem.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_WORKITEM</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551203">WdfWorkItemEnqueue</a>
 

 

