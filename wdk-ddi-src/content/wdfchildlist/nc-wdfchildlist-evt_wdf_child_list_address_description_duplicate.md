---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE
title: EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE (wdfchildlist.h)
description: A driver's EvtChildListAddressDescriptionDuplicate event callback function duplicates a child address description.
old-location: wdf\evtchildlistaddressdescriptionduplicate.htm
tech.root: wdf
ms.assetid: 3b99401c-5a36-4ccd-b3a4-c5687310c29b
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_5ade5582-8a35-49cb-a291-e6d972822138.xml, EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE, EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE callback, EvtChildListAddressDescriptionDuplicate, EvtChildListAddressDescriptionDuplicate callback function, kmdf.evtchildlistaddressdescriptionduplicate, wdf.evtchildlistaddressdescriptionduplicate, wdfchildlist/EvtChildListAddressDescriptionDuplicate
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
-	EvtChildListAddressDescriptionDuplicate
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListAddressDescriptionDuplicate</i> event callback function duplicates a child address description.


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


### -param SourceAddressDescription [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551219">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies the source location of the child address description.


### -param DestinationAddressDescription [out]

A pointer to a WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure that identifies the destination location of the child address description.


## -returns



The <i>EvtChildListAddressDescriptionDuplicate</i> callback function must return STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if the operation succeeds. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



If a bus driver is using <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListAddressDescriptionDuplicate</i> callback function by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547258">WdfFdoInitSetDefaultChildListConfig</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545615">WdfChildListCreate</a>.

The framework duplicates driver-supplied address descriptions so that it can have internal copies of the descriptions.

The <i>EvtChildListAddressDescriptionDuplicate</i> callback function must create a duplicate copy of an address description. A driver must supply this callback function if its child devices require an address description, and if the framework cannot call <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a> to duplicate the address description. (The framework cannot call <b>RtlCopyMemory</b> if the description contains pointers to additional memory.)

If your driver provides address descriptions but does not provide a <i>EvtChildListAddressDescriptionDuplicate</i> callback function, the framework duplicates address descriptions by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a>.

The following steps describe a typical scenario:

<ol>
<li>
The driver determines that a child device exists.

</li>
<li>
The driver creates an address description by filling in a driver-defined structure that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551219">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure and possibly by dynamically allocating additional memory to store address information that has a device-specific size. 

</li>
<li>
The driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545591">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> to report a child device, supplying a pointer to the address description. 

</li>
<li>
The framework calls the <i>EvtChildListAddressDescriptionDuplicate</i> callback function (if it exists) or <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a> to duplicate the address description so that it can have an internal copy of the description.

</li>
</ol>
The framework can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a> to duplicate an address description, if the description consists of a single structure with a predetermined size that is specified by the <b>AddressDescriptionSize</b> member of the WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListAddressDescriptionDuplicate</i> callback function. The callback function must do the following:

<ol>
<li>
Allocate additional memory, typically by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544501">ExAllocatePool</a>.

</li>
<li>
Store the allocated memory's address in the driver-defined address description structure (that is, the callback function's <i>DestinationAddressDescription</i> structure).

</li>
<li>
Copy other structure members from the callback function's <i>SourceAddressDescription</i> structure to the callback function's <i>DestinationAddressDescription</i> structure.

</li>
</ol>
The only <a href="https://msdn.microsoft.com/BFD91F00-5D35-4AF8-A6B6-F27DF64605D8">framework child-list object method</a> that a driver's <i>EvtChildListAddressDescriptionDuplicate</i> callback function can call is <a href="https://msdn.microsoft.com/library/windows/hardware/ff545636">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListAddressDescriptionDuplicate</i> callback function. The callback function must only perform operations that are related to the described duplication operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

If your driver supplies an <i>EvtChildListAddressDescriptionDuplicate</i> callback function, it might also need <a href="https://msdn.microsoft.com/b73ec39c-8d93-4992-8791-5070a088701a">EvtChildListAddressDescriptionCopy</a> and <a href="https://msdn.microsoft.com/845c8c96-7d34-4273-963e-b7f644884f26">EvtChildListAddressDescriptionCleanup</a> callback functions.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a><u>.</u>


#### Examples

To define an <i>EvtChildListAddressDescriptionDuplicate</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListAddressDescriptionDuplicate</i> callback function that is named <i>MyChildListAddressDescriptionDuplicate</i>, use the <b>EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE MyChildListAddressDescriptionDuplicate;</pre>
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
NTSTATUS
 MyChildListAddressDescriptionDuplicate (
 WDFCHILDLIST  ChildList,
    PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER  SourceAddressDescription,
    PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER  DestinationAddressDescription
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The_Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/845c8c96-7d34-4273-963e-b7f644884f26">EvtChildListAddressDescriptionCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544501">ExAllocatePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551219">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545591">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545615">WdfChildListCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545636">WdfChildListGetDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547258">WdfFdoInitSetDefaultChildListConfig</a>
 

 

