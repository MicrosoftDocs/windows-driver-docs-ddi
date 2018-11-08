---
UID: NC:ndis.FILTER_RETURN_NET_BUFFER_LISTS
title: FILTER_RETURN_NET_BUFFER_LISTS
author: windows-driver-content
description: NDIS calls the FilterReturnNetBufferLists function to return a linked list of NET_BUFFER_LIST structures and associated data to a filter driver.Note  You must declare the function by using the FILTER_RETURN_NET_BUFFER_LISTS type.
old-location: netvista\filterreturnnetbufferlists.htm
tech.root: netvista
ms.assetid: 8d7e362f-62da-4ce7-9497-1cfaff2b678e
ms.date: 05/02/2018
ms.keywords: FILTER_RETURN_NET_BUFFER_LISTS, FILTER_RETURN_NET_BUFFER_LISTS callback, FilterReturnNetBufferLists, FilterReturnNetBufferLists callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_a4a0c4ae-790b-43f9-a209-06538a7bbab6.xml, ndis/FilterReturnNetBufferLists, netvista.filterreturnnetbufferlists
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
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
-	Ndis.h
api_name:
-	FilterReturnNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
---

# FILTER_RETURN_NET_BUFFER_LISTS callback function


## -description


NDIS calls the 
  <i>FilterReturnNetBufferLists</i> function to return a linked list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures and associated data
  to a filter driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_RETURN_NET_BUFFER_LISTS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param NetBufferLists [in]

A linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that the filter driver indicated by calling the 
     <a href="https://msdn.microsoft.com/ff2457bb-158a-411c-8c6b-7a7e402497ef">
     NdisFIndicateReceiveNetBufferLists</a> function. The list can include <b>NET_BUFFER_LIST</b> structures from
     multiple calls to 
     <b>NdisFIndicateReceiveNetBufferLists</b>.


### -param ReturnFlags [in]

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero.This function supports the following flags: 





#### NDIS_RETURN_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_RETURN_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="https://msdn.microsoft.com/FBA506EC-4E9F-4964-9C9C-FF4910DDA908">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_RECEIVE_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>ReceiveFlags</i> parameter of <a href="https://msdn.microsoft.com/6359c2a7-1208-41ea-bbf9-015c91b6e8f6">FilterReceiveNetBufferLists</a>  when it sends the request.</div>
<div> </div>

## -returns



None




## -remarks



<i>FilterReturnNetBufferLists</i> is an optional function. If a filter driver does not filter receive indications, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> function.

The filter driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function,
    from the 
    <a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">FilterSetModuleOptions</a> function, to
    specify a 
    <i>FilterReturnNetBufferLists</i> function for a filter module.

<div class="alert"><b>Note</b>  A filter driver that does not provide a 
    <i>FilterReturnNetBufferLists</i> function cannot call the 
    <a href="https://msdn.microsoft.com/ff2457bb-158a-411c-8c6b-7a7e402497ef">
    NdisFIndicateReceiveNetBufferLists</a> function to initiate a receive indication.</div>
<div> </div>
<div class="alert"><b>Note</b>  A filter driver that does provide a 
    <i>FilterReturnNetBufferLists</i> function must provide a 
    <a href="https://msdn.microsoft.com/051ce37c-a7a5-4367-9495-023fc51349ba">FilterStatus</a> function.</div>
<div> </div>
When NDIS calls 
    <i>FilterReturnNetBufferLists</i>, the filter driver regains ownership of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures and associated
    data.

If an underlying driver initiated the receive indication, the filter driver should call the 
    <a href="https://msdn.microsoft.com/083cf25d-7436-4c4e-b29a-c9a2702b136d">
    NdisFReturnNetBufferLists</a> function to complete the receive indication.

If the filter driver originated the receive indication, 
    <i>FilterReturnNetBufferLists</i> can either release the NET_BUFFER_LIST structures and associated data or
    prepare them for reuse in a subsequent call to 
    <b>NdisFIndicateReceiveNetBufferLists</b>.

A filter driver should keep track of receive indications that it initiates and make sure that it does
    not call 
    <b>NdisFReturnNetBufferLists</b> when NDIS calls 
    <i>FilterReturnNetBufferLists</i>.

NDIS calls 
    <i>FilterReturnNetBufferLists</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterReturnNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterReturnNetBufferLists</i> function that is named "MyReturnNetBufferLists", use the <b>FILTER_RETURN_NET_BUFFER_LISTS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_RETURN_NET_BUFFER_LISTS MyReturnNetBufferLists;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyReturnNetBufferLists(
    NDIS_HANDLE  FilterModuleContext,
    PNET_BUFFER_LIST  NetBufferLists,
    ULONG  ReturnFlags
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_RETURN_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_RETURN_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">FilterSetModuleOptions</a>



<a href="https://msdn.microsoft.com/051ce37c-a7a5-4367-9495-023fc51349ba">FilterStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/ff2457bb-158a-411c-8c6b-7a7e402497ef">
   NdisFIndicateReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562613">NdisFReturnNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 

