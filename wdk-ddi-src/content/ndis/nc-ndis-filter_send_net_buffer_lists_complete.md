---
UID: NC:ndis.FILTER_SEND_NET_BUFFER_LISTS_COMPLETE
title: FILTER_SEND_NET_BUFFER_LISTS_COMPLETE (ndis.h)
description: NDIS calls the FilterSendNetBufferListsComplete function to complete a send request that a filter driver started by calling the NdisFSendNetBufferLists function.Note  You must declare the function by using the FILTER_SEND_NET_BUFFER_LISTS_COMPLETE type.
old-location: netvista\filtersendnetbufferlistscomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FILTER_SEND_NET_BUFFER_LISTS_COMPLETE callback function"]
ms.keywords: FILTER_SEND_NET_BUFFER_LISTS_COMPLETE, FILTER_SEND_NET_BUFFER_LISTS_COMPLETE callback, FilterSendNetBufferListsComplete, FilterSendNetBufferListsComplete callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_5022c19b-6433-4c57-aa68-20270400950b.xml, ndis/FilterSendNetBufferListsComplete, netvista.filtersendnetbufferlistscomplete
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FILTER_SEND_NET_BUFFER_LISTS_COMPLETE
 - ndis/FILTER_SEND_NET_BUFFER_LISTS_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - FilterSendNetBufferListsComplete
---

# FILTER_SEND_NET_BUFFER_LISTS_COMPLETE callback function


## -description

NDIS calls the 
  <i>FilterSendNetBufferListsComplete</i> function to complete a send request that a filter driver started by
  calling the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlists">
  NdisFSendNetBufferLists</a> function.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_SEND_NET_BUFFER_LISTS_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param FilterModuleContext 

[in]
A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param NetBufferList

A pointer to a linked list of 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that the filter
     driver passed to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlists">
  NdisFSendNetBufferLists</a>.

### -param SendCompleteFlags 

[in]
NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to zero. This function supports the following flags:





#### NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
        <a href="/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.



#### NDIS_SEND_COMPLETE_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-send-and-receive-flags">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_SEND_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>SendFlags</i> parameter of <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_send_net_buffer_lists">SendNetBufferLists</a> when it sends the request.</div>
<div> </div>
<div class="alert"><b>Note</b>  This flag is available in NDIS 6.30 and later.</div>
<div> </div>

## -remarks

<i>FilterSendNetBufferListsComplete</i> is an optional function. If a filter driver does not filter send
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function.

The filter driver can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a> function,
    from the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_set_module_options">FilterSetModuleOptions</a> function,
    to specify a 
    <i>FilterSendNetBufferListsComplete</i> function for a filter module.

<div class="alert"><b>Note</b>  A filter driver that does not provide a 
    <i>FilterSendNetBufferListsComplete</i> function cannot call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlists">NdisFSendNetBufferLists</a> function.</div>
<div> </div>
When NDIS calls 
    <i>FilterSendNetBufferListsComplete</i>, the filter driver regains ownership of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures and associated
    data.

If an overlying driver initiated the send request, the filter driver should call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlistscomplete">NdisFSendNetBufferListsComplete</a> function to complete the send request.

If the filter driver originated the send request, 
    <i>FilterSendNetBufferListsComplete</i> can either release the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures and associated
    data or prepare them for reuse in a subsequent call to 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlists">NdisFSendNetBufferLists</a>.

<div class="alert"><b>Note</b>  A filter driver should keep track of send requests that it initiates and make sure that it does not
    call 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlistscomplete">NdisFSendNetBufferListsComplete</a> when NDIS calls 
    <i>FilterSendNetBufferListsComplete</i> for such requests.</div>
<div> </div>
NDIS calls 
    <i>FilterSendNetBufferListsComplete</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterSendNetBufferListsComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterSendNetBufferListsComplete</i> function that is named "MySendNetBufferListsComplete", use the <b>FILTER_SEND_NET_BUFFER_LISTS_COMPLETE</b> type as shown in this code example:


```
FILTER_SEND_NET_BUFFER_LISTS_COMPLETE MySendNetBufferListsComplete;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MySendNetBufferListsComplete(
    NDIS_HANDLE  FilterModuleContext,
    PNET_BUFFER_LIST  NetBufferLists,
    ULONG  SendCompleteFlags
    )
  {...}
```

The <b>FILTER_SEND_NET_BUFFER_LISTS_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_SEND_NET_BUFFER_LISTS_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_set_module_options">FilterSetModuleOptions</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlists">NdisFSendNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsendnetbufferlistscomplete">
   NdisFSendNetBufferListsComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>
