---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP
title: EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP
author: windows-driver-content
description: A driver's EvtChildListIdentificationDescriptionCleanup event callback function frees any memory allocations for an identification description that the driver's EvtChildListIdentificationDescriptionDuplicate callback function allocated.
old-location: wdf\evtchildlistidentificationdescriptioncleanup.htm
old-project: wdf
ms.assetid: 4874f03e-b4e7-4fae-8737-7630462cd7e5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_f70d9bc7-a6f9-41c4-a6c3-7a9ef413096c.xml, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP, EvtChildListIdentificationDescriptionCleanup, EvtChildListIdentificationDescriptionCleanup callback function, kmdf.evtchildlistidentificationdescriptioncleanup, wdf.evtchildlistidentificationdescriptioncleanup, wdfchildlist/EvtChildListIdentificationDescriptionCleanup
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
-	EvtChildListIdentificationDescriptionCleanup
product: Windows
targetos: Windows
req.typenames: WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO
req.product: Windows 10 or later.
---

# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtChildListIdentificationDescriptionCleanup</i> event callback function frees any memory allocations for an identification description that the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate.md">EvtChildListIdentificationDescriptionDuplicate</a> callback function allocated.


## -prototype


````
EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP EvtChildListIdentificationDescriptionCleanup;

VOID EvtChildListIdentificationDescriptionCleanup(
  _In_    WDFCHILDLIST                                 ChildList,
  _Inout_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER IdentificationDescription
)
{ ... }
````


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


### -param IdentificationDescription [in, out]

A pointer to a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies an identification description.


## -returns



None




## -remarks



If a bus driver is using <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionCleanup</i> callback function by calling <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>.

If an identification description points to additional information that is stored in dynamically allocated memory, and if that memory is allocated by an <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate.md">EvtChildListIdentificationDescriptionDuplicate</a> callback function, the driver must provide an <i>EvtChildListIdentificationDescriptionCleanup</i> callback function. 

Typically, the <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate.md">EvtChildListIdentificationDescriptionDuplicate</a> callback function allocates memory by calling <a href="..\wdm\nf-wdm-exallocatepool.md">ExAllocatePool</a>. The <i>EvtChildListIdentificationDescriptionCleanup</i> callback function must deallocate that memory by calling <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>. This callback function must not attempt to deallocate the rest of the identification description. In other words, the callback function must not deallocate the address description structure that the <i>IdentificationDescription</i> parameter points to; it must deallocate only additional memory allocations that the description structure points to.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

To define an <i>EvtChildListIdentificationDescriptionCleanup</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListIdentificationDescriptionCleanup</i> callback function that is named <i>MyChildListIdentificationDescriptionCleanup</i>, use the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP  MyChildListIdentificationDescriptionCleanup;</pre>
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
 MyChildListIdentificationDescriptionCleanup (
 WDFCHILDLIST  ChildList,
    PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER  IdentificationDescription
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>



<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate.md">EvtChildListIdentificationDescriptionDuplicate</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>



<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>



<a href="..\wdm\nf-wdm-exallocatepool.md">ExAllocatePool</a>



 

 


