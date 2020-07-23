---
UID: NC:ndkpi.NDK_FN_GET_LISTENER_LOCAL_ADDRESS
title: NDK_FN_GET_LISTENER_LOCAL_ADDRESS (ndkpi.h)
description: The NdkGetListenerLocalAddress (NDK_FN_GET_LISTENER_LOCAL_ADDRESS) function returns the local address for an NDK listener.
old-location: netvista\ndk_fn_get_listener_local_address.htm
tech.root: netvista
ms.assetid: 7BF5322F-5283-445D-AC3F-19382CB28E2B
ms.date: 05/02/2018
keywords: ["NDK_FN_GET_LISTENER_LOCAL_ADDRESS callback function"]
ms.keywords: NDK_FN_GET_LISTENER_LOCAL_ADDRESS, NDK_FN_GET_LISTENER_LOCAL_ADDRESS callback, NdkGetListenerLocalAddress, NdkGetListenerLocalAddress callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetListenerLocalAddress, netvista.ndk_fn_get_listener_local_address
f1_keywords:
 - "ndkpi/NdkGetListenerLocalAddress"
 - "NdkGetListenerLocalAddress"
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkGetListenerLocalAddress
targetos: Windows
req.typenames: 
---

# NDK_FN_GET_LISTENER_LOCAL_ADDRESS callback function


## -description


The <i>NdkGetListenerLocalAddress</i> (<i>NDK_FN_GET_LISTENER_LOCAL_ADDRESS</i>) function returns the local address for an NDK  listener.


## -parameters




### -param pNdkListener [in]

A pointer to an NDK listener object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_listener">NDK_LISTENER</a>).


### -param pAddress

A local address for a listener is returned in this buffer.


### -param pAddressLength

The size, in bytes, of the address buffer for input, and the size, in bytes, of the actual address written into the buffer for output.


## -returns



The 
     <i>NdkGetListenerLocalAddress</i> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
A local address was written to the buffer in the <i>pAddress</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer size specified in the <i>*pAddressLength</i> parameter input is too small. <i>*pAddressLength</i> output value is updated with the required buffer size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>
 




## -remarks



<i>NdkGetListenerLocalAddress</i> returns the local address for a listener. The local address is useful for retrieving port information for an AF_INET or AF_INET6 listener. For example, if the NDK consumer specifies zero as the ND port number in a listen request and the NDK provider specifies a port, the NDK consumer can use <i>NdkGetListenerLocalAddress</i> to  determine which port the provider specified.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_listen">NDK_FN_LISTEN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_listener">NDK_LISTENER</a>
 

 

