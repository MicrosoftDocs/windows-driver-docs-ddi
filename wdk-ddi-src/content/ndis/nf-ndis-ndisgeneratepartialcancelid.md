---
UID: NF:ndis.NdisGeneratePartialCancelId
title: NdisGeneratePartialCancelId function
author: windows-driver-content
description: The NdisGeneratePartialCancelId function returns a value that the calling driver must use as the high-order byte of a cancellation ID.
old-location: netvista\ndisgeneratepartialcancelid.htm
old-project: netvista
ms.assetid: a26e9602-058b-401b-85be-9d80e4ef213b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisGeneratePartialCancelId, NdisGeneratePartialCancelId function [Network Drivers Starting with Windows Vista], ndis/NdisGeneratePartialCancelId, netvista.ndisgeneratepartialcancelid, protocol_ndis_functions_ref_0d6b9e5a-d346-46a0-8f1c-d6677df53f1c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGeneratePartialCancelId   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGeneratePartialCancelId   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
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
-	NdisGeneratePartialCancelId
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGeneratePartialCancelId function


## -description


The
  <b>NdisGeneratePartialCancelId</b> function returns a value that the calling driver must use as the
  high-order byte of a cancellation ID.


## -parameters






## -returns



<b>NdisGeneratePartialCancelId</b> returns a value that the calling driver uses as the high-order byte of
     a cancellation ID.




## -remarks



Before marking send 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures with cancellation
    IDs by calling the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567299">
    NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a> macro, a driver should call 
    <b>NdisGeneratePartialCancelId</b> one or more times. 
    <b>NdisGeneratePartialCancelId</b> returns a value that the calling driver can use as the high-order byte
    of a cancellation ID. Prefixing a cancellation ID with the value returned by 
    <b>NdisGeneratePartialCancelId</b> ensures that the cancellation ID will not be a duplicate of a
    cancellation ID assigned by another driver in the local computer.

Typically, an overlying driver calls 
    <b>NdisGeneratePartialCancelId</b> one or more times during its initialization sequence and stores the
    returned value or values for later use. A protocol driver, for example, could call 
    <b>NdisGeneratePartialCancelId</b> once for each client (such as DHCP or ARC) that it supports. The
    protocol driver can call the 
    <a href="https://msdn.microsoft.com/7b61db73-ddd4-4d46-b378-9a82fdf041ea">
    NdisCancelSendNetBufferLists</a> function later to cancel a send request. In this case, NDIS calls the
    cancel send function (for example, 
    <a href="https://msdn.microsoft.com/17111aa3-c02f-494a-af97-5ab34c152451">MiniportCancelSend</a>) of the
    underlying drivers.




## -see-also




<a href="https://msdn.microsoft.com/17111aa3-c02f-494a-af97-5ab34c152451">MiniportCancelSend</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567299">
   NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561623">NdisCancelSendNetBufferLists</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGeneratePartialCancelId function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

