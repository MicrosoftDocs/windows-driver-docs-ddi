---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY
title: EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY
author: windows-driver-content
description: A driver's EvtChildListIdentificationDescriptionCopy event callback function copies a child identification description from one specified location to another.
old-location: wdf\evtchildlistidentificationdescriptioncopy.htm
tech.root: wdf
ms.assetid: c44d6a2f-c7ef-486d-973e-aada068ddc06
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_8568b87d-544a-4574-a9c7-c5498a30a758.xml, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY callback, EvtChildListIdentificationDescriptionCopy, EvtChildListIdentificationDescriptionCopy callback function, kmdf.evtchildlistidentificationdescriptioncopy, wdf.evtchildlistidentificationdescriptioncopy, wdfchildlist/EvtChildListIdentificationDescriptionCopy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfchildlist.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	WdfChildlist.h
api_name:
-	EvtChildListIdentificationDescriptionCopy
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListIdentificationDescriptionCopy</i> event callback function copies a child identification description from one specified location to another.


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


### -param SourceIdentificationDescription [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the source location of the child identification description.


### -param DestinationIdentificationDescription [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the destination location of the child identification description.


## -returns



None




## -remarks



If a bus driver is using <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionCopy</i> callback function by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547258">WdfFdoInitSetDefaultChildListConfig</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545615">WdfChildListCreate</a>.

The framework copies information from one driver-supplied identification description to another when it needs to update an existing description with new information, or when it needs to pass the contents of an identification description to the driver.

The <i>EvtChildListIdentificationDescriptionCopy</i> callback function must copy the contents of a source description to a destination description. A driver must supply this callback function if the framework cannot call <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a> to copy the identification description. (The framework cannot call <b>RtlCopyMemory</b> if the description contains pointers to additional memory.)

If your driver does not provide an <i>EvtChildListIdentificationDescriptionCopy</i> callback function, the framework copies identification descriptions by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a>.

The following steps describe a possible scenario:

<ol>
<li>
The driver that is traversing a child list calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a>. The driver supplies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551234">WDF_CHILD_RETRIEVE_INFO</a> structure so that it can receive the child device's identification description.

</li>
<li>
The framework calls the <i>EvtChildListIdentificationDescriptionCopy</i> callback function (if it exists) or <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a> to copy the device's identification description. The source of the copy operation is the framework's internal copy of the description. The destination is memory that the driver allocated and identified in its WDF_CHILD_RETRIEVE_INFO structure.

</li>
</ol>
The framework can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a> to copy an identification description, if the description consists of a single structure with a predetermined size that is specified by the <b>IdentificationDescriptionSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListIdentificationDescriptionCopy</i> callback function. The callback function must do the following:

<ol>
<li>
In the callback function's <i>SourceIdentificationDescription</i> and <i>DestinationIdentificationDescription</i> structures, find the pointers to dynamically allocated memory.

</li>
<li>
Copy the dynamically allocated memory from the source to the destination, using the pointers.

</li>
<li>
Copy other structure members from the callback function's <i>SourceIdentificationDescription</i> structure to the callback function's <i>DestinationIdentificationDescription</i> structure.

</li>
</ol>
The only <a href="https://msdn.microsoft.com/BFD91F00-5D35-4AF8-A6B6-F27DF64605D8">framework child-list object method</a> that a driver's <i>EvtChildListIdentificationDescriptionCopy</i> callback function can call is <a href="https://msdn.microsoft.com/library/windows/hardware/ff545636">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListIdentificationDescriptionCopy</i> callback function. The callback function must only perform operations that are related to the copy operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

If your driver supplies an <i>EvtChildListIdentificationDescriptionCopy</i> callback function, it might also need <a href="https://msdn.microsoft.com/5c2ec27c-2d88-4e0c-8f11-4f58d720df46">EvtChildListIdentificationDescriptionDuplicate</a>, <a href="https://msdn.microsoft.com/b807f9f8-588f-4303-be97-a9fd4cff2bbd">EvtChildListIdentificationDescriptionCompare</a>, and <a href="https://msdn.microsoft.com/4874f03e-b4e7-4fae-8737-7630462cd7e5">EvtChildListIdentificationDescriptionCleanup</a> callback functions.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

To define an <i>EvtChildListIdentificationDescriptionCopy</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListIdentificationDescriptionCopy</i> callback function that is named <i>MyChildListIdentificationDescriptionCopy</i>, use the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION</b> type as shown in this code example:

To define an <i>EvtChildListIdentificationDescriptionCopy</i> callback function that is named <b>MyChildListIdentificationDescriptionCopy</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY  MyChildListIdentificationDescriptionCopy;</pre>
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
<pre>
_Use_decl_annotations_
VOID
 MyChildListIdentificationDescriptionCopy (
 WDFCHILDLIST  ChildList,
    PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER  SourceIdentificationDescription,
    PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER  DestinationIdentificationDescription
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/4874f03e-b4e7-4fae-8737-7630462cd7e5">EvtChildListIdentificationDescriptionCleanup</a>



<a href="https://msdn.microsoft.com/b807f9f8-588f-4303-be97-a9fd4cff2bbd">EvtChildListIdentificationDescriptionCompare</a>



<a href="https://msdn.microsoft.com/5c2ec27c-2d88-4e0c-8f11-4f58d720df46">EvtChildListIdentificationDescriptionDuplicate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545615">WdfChildListCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545636">WdfChildListGetDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547258">WdfFdoInitSetDefaultChildListConfig</a>
 

 

