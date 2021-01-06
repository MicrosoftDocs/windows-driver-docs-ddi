---
UID: NC:ndis.MINIPORT_CO_SEND_NET_BUFFER_LISTS
title: MINIPORT_CO_SEND_NET_BUFFER_LISTS (ndis.h)
description: The MiniportCoSendNetBufferLists function transmits network data that is contained in a specified linked list of NET_BUFFER_LIST structures.Note  You must declare the function by using the MINIPORT_CO_SEND_NET_BUFFER_LISTS type.
old-location: netvista\miniportcosendnetbufferlists.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_CO_SEND_NET_BUFFER_LISTS callback function"]
ms.keywords: MINIPORT_CO_SEND_NET_BUFFER_LISTS, MINIPORT_CO_SEND_NET_BUFFER_LISTS callback, MiniportCoSendNetBufferLists, MiniportCoSendNetBufferLists callback function [Network Drivers Starting with Windows Vista], condis_sendrcv_ref_28cddc06-235d-4274-a783-554dec10ad84.xml, ndis/MiniportCoSendNetBufferLists, netvista.miniportcosendnetbufferlists
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
 - MINIPORT_CO_SEND_NET_BUFFER_LISTS
 - ndis/MINIPORT_CO_SEND_NET_BUFFER_LISTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - MiniportCoSendNetBufferLists
---

# MINIPORT_CO_SEND_NET_BUFFER_LISTS callback function


## -description

The 
  <i>MiniportCoSendNetBufferLists</i> function transmits network data that is contained in a specified linked
  list of 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CO_SEND_NET_BUFFER_LISTS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportVcContext 

[in]
A handle to a miniport driver-allocated context area in which the miniport driver maintains its
     per-virtual connection (VC) state. The miniport driver supplied this handle to NDIS from its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function.

### -param NetBufferLists 

[in]
A pointer to the first 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure in a linked list
     of <b>NET_BUFFER_LIST</b> structures. Each <b>NET_BUFFER_LIST</b> structure in the list describes a list of 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures. Each <b>NET_BUFFER</b> structure
     in the list maps to a chain of memory descriptor lists (MDLs). The MDLs contain the network data that 
     <i>MiniportCoSendNetBufferLists</i> transmits.

### -param SendFlags 

[in]
Flags that define attributes for the send operation. The flags can be combined with a bitwise OR
     operation. To clear all of the flags, set this parameter to zero. 
     <i>MiniportCoSendNetBufferLists</i> supports the following flags:
     





#### NDIS_SEND_FLAGS_DISPATCH_LEVEL

The caller can optionally set this flag if the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.



#### NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK

NDIS should check for loopback. By default, NDIS does not loop back data to the driver that
       submitted the send request. An overlying driver can override this behavior by setting the
       <b>NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK</b> flag. When this flag is set, NDIS identifies all of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>
       structures that contain data that matches the receive criteria for the binding. NDIS indicates
       <b>NET_BUFFER</b> structures that match the criteria to the overlying driver. This flag does not affect
       checking for loopback, or looping back, on other bindings.

## -remarks

The 
    <i>MiniportCoSendNetBufferLists</i> function is required for CoNDIS miniport drivers. When an overlying
    driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscosendnetbufferlists">
    NdisCoSendNetBufferLists</a> function, NDIS calls the 
    <i>MiniportCoSendNetBufferLists</i> function of the bound miniport driver.

The order of the linked list of 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures that NDIS passes
    at 
    <i>NetBufferLists</i> represents the order in which the miniport driver should transmit the network data.
    In addition, a miniport driver should send the <b>NET_BUFFER_LIST</b> structures from multiple 
    <i>MiniportCoSendNetBufferLists</i> calls in the order that the miniport driver received the structures
    in.

CoNDIS miniport drivers must accept all of the send requests that NDIS makes by calling the 
    <i>MiniportCoSendNetBufferLists</i> function. If a miniport driver cannot complete a send request
    immediately, the driver must hold the request in a queue until it can complete the request. While a send
    request is pending, the miniport driver retains ownership of the <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures and all of
    the resources that are associated with the <b>NET_BUFFER_LIST</b> structures.

The miniport driver must call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcosendnetbufferlistscomplete">
    NdisMCoSendNetBufferListsComplete</a> function to complete all CoNDIS send requests. To improve
    computer performance, the driver can create a linked list that contains the 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures from multiple
    send requests. The driver can then pass such a linked list in a single call to 
    <b>NdisMCoSendNetBufferListsComplete</b>.

In addition, you should assume that the miniport driver cannot access the <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structures
    and other associated resources as soon as the driver calls 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcosendnetbufferlistscomplete">NdisMCoSendNetBufferListsComplete</a>.

The 
    <i>MiniportCoSendNetBufferLists</i> function must synchronize access to its internal queues of network
    data with the driver's other 
    <i>MiniportXxx</i> functions that access the same queues. A miniport driver can use spin locks to
    synchronize access to the queues.

Protocol drivers are responsible for determining what network data is required, based on the medium
    type that the bound miniport driver selected. However, a protocol driver can supply network data that
    specifies packets that are shorter than the minimum packet size for the selected medium. In this case, 
    <i>MiniportCoSendNetBufferLists</i> must pad the packets with zeros if the selected medium imposes a
    minimum-length requirement on the transmit packet size.

NDIS calls 
    <i>MiniportCoSendNetBufferLists</i> at IRQL<= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCoSendNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCoSendNetBufferLists</i> function that is named "MyCoSendNetBufferLists", use the <b>MINIPORT_CO_SEND_NET_BUFFER_LISTS</b> type as shown in this code example:


```
MINIPORT_CO_SEND_NET_BUFFER_LISTS MyCoSendNetBufferLists;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyCoSendNetBufferLists(
    NDIS_HANDLE  MiniportVcContext,
    PNET_BUFFER_LIST  NetBufferLists,
    ULONG  SendFlags
    )
  {...}
```

The <b>MINIPORT_CO_SEND_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_SEND_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscosendnetbufferlists">NdisCoSendNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcosendnetbufferlistscomplete">
   NdisMCoSendNetBufferListsComplete</a>
