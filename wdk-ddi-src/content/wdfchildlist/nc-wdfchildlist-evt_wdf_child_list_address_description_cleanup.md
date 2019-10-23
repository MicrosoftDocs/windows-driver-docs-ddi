---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP
title: EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP (wdfchildlist.h)
description: A driver's EvtChildListAddressDescriptionCleanup event callback function frees any memory allocations for an address description that the driver's EvtChildListAddressDescriptionDuplicate callback function allocated.
old-location: wdf\evtchildlistaddressdescriptioncleanup.htm
tech.root: wdf
ms.assetid: 845c8c96-7d34-4273-963e-b7f644884f26
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_f28ee1b8-ff52-416e-9811-1eb46939505a.xml, EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP, EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP callback, EvtChildListAddressDescriptionCleanup, EvtChildListAddressDescriptionCleanup callback function, kmdf.evtchildlistaddressdescriptioncleanup, wdf.evtchildlistaddressdescriptioncleanup, wdfchildlist/EvtChildListAddressDescriptionCleanup
ms.topic: callback
f1_keywords:
 - "wdfchildlist/EvtChildListAddressDescriptionCleanup"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfChildlist.h
api_name:
- EvtChildListAddressDescriptionCleanup
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListAddressDescriptionCleanup</i> event callback function frees any memory allocations for an <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a> that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_duplicate">EvtChildListAddressDescriptionDuplicate</a> callback function allocated.


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


### -param AddressDescription [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies an address description.


## -returns



None




## -remarks



If a bus driver is using <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListAddressDescriptionCleanup</i> callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>.

If an address description points to additional information that is stored in dynamically allocated memory, and if that memory is allocated by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_duplicate">EvtChildListAddressDescriptionDuplicate</a> callback function, the driver must provide an <i>EvtChildListAddressDescriptionCleanup</i> callback function. 

Typically, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_duplicate">EvtChildListAddressDescriptionDuplicate</a> callback function allocates memory by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepool">ExAllocatePool</a>. The <i>EvtChildListAddressDescriptionCleanup</i> callback function must deallocate that memory by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>. This callback function must not attempt to deallocate the rest of the address description. In other words, the callback function must not deallocate the address description structure that the <i>AddressDescription</i> parameter points to; it must deallocate only additional memory allocations that the description structure points to.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a><u>.</u>


#### Examples

To define an <i>EvtChildListAddressDescriptionCleanup</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListAddressDescriptionCleanup</i> callback function that is named <i>MyChildListAddressDescriptionCleanup</i>, use the <b>EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP  MyChildListAddressDescriptionCleanup;</pre>
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
 MyChildListAddressDescriptionCleanup (
    WDFCHILDLIST  ChildList,
    PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER  AddressDescription
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_duplicate">EvtChildListAddressDescriptionDuplicate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepool">ExAllocatePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>
 

 

