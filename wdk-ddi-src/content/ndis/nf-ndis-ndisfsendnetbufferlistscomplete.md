---
UID: NF:ndis.NdisFSendNetBufferListsComplete
title: NdisFSendNetBufferListsComplete function
description: Filter drivers call the NdisFSendNetBufferListsComplete function to return a linked list of NET_BUFFER_LIST structures to an overlying driver and to return the final status of a send request.
old-location: netvista\ndisfsendnetbufferlistscomplete.htm
tech.root: netvista
ms.assetid: 5a9008eb-86ad-4e3c-85a2-c8fd1b8fb4cb
ms.date: 05/02/2018
ms.keywords: NdisFSendNetBufferListsComplete, NdisFSendNetBufferListsComplete function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_376e31a2-453d-490e-83bb-b91b728f701f.xml, ndis/NdisFSendNetBufferListsComplete, netvista.ndisfsendnetbufferlistscomplete
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFSendNetBufferListsComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFSendNetBufferListsComplete function


## -description


Filter drivers call the 
  <b>NdisFSendNetBufferListsComplete</b> function to return a linked list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures to an overlying
  driver and to return the final status of a send request.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param NetBufferList

A pointer to a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures. The filter driver received the
     <b>NET_BUFFER_LIST</b> structures in previous calls to the 
     <a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">
     FilterSendNetBufferLists</a> function.


### -param SendCompleteFlags [in]

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to zero. This function supports the following flags:





#### NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
        <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_SEND_COMPLETE_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="https://msdn.microsoft.com/FBA506EC-4E9F-4964-9C9C-FF4910DDA908">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_SEND_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>SendFlags</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff562616">NdisFSendNetBufferLists</a> when it sends the request.</div>
<div> </div>
<div class="alert"><b>Note</b>  This flag is available in NDIS 6.30 and later.</div>
<div> </div>

## -returns



None




## -remarks



A filter driver calls the 
    <b>NdisFSendNetBufferListsComplete</b> function to complete send requests that NDIS made to the driver's 
    <a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">
    FilterSendNetBufferLists</a> function. The filter driver specifies a linked list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are
    associated with the completed send requests. While the status of the send requests is pending, the filter
    driver retains ownership of the <b>NET_BUFFER_LIST</b> structures and all the resources that are associated with
    the <b>NET_BUFFER_LIST</b> structures.

The filter driver can complete send requests in any order. For example, the filter driver could
    concatenate the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure lists from multiple 
    <a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">FilterSendNetBufferLists</a> calls or split up a list from a 
    <i>FilterSendNetBufferLists</i> call. However, the filter driver must not modify the list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures that are associated with a
    <b>NET_BUFFER_LIST</b> structure.

<div class="alert"><b>Note</b>  A filter driver should keep track of send requests that it originates and make
      sure that it does not call the 
      <b>
      NdisFSendNetBufferListsComplete</b> function when such requests are complete.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">FilterSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
 

 

