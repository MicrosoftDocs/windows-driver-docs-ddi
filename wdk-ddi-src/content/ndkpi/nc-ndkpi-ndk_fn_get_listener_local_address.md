---
UID: NC:ndkpi.NDK_FN_GET_LISTENER_LOCAL_ADDRESS
title: NDK_FN_GET_LISTENER_LOCAL_ADDRESS
author: windows-driver-content
description: The NdkGetListenerLocalAddress (NDK_FN_GET_LISTENER_LOCAL_ADDRESS) function returns the local address for an NDK listener.
old-location: netvista\ndk_fn_get_listener_local_address.htm
old-project: netvista
ms.assetid: 7BF5322F-5283-445D-AC3F-19382CB28E2B
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_FN_GET_LISTENER_LOCAL_ADDRESS, NdkGetListenerLocalAddress, NdkGetListenerLocalAddress callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetListenerLocalAddress, netvista.ndk_fn_get_listener_local_address
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndkpi.h
api_name:
-	NdkGetListenerLocalAddress
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_GET_LISTENER_LOCAL_ADDRESS callback


## -description


The <i>NdkGetListenerLocalAddress</i> (<i>NDK_FN_GET_LISTENER_LOCAL_ADDRESS</i>) function returns the local address for an NDK  listener.


## -prototype


````
NDK_FN_GET_LISTENER_LOCAL_ADDRESS NdkGetListenerLocalAddress;

NTSTATUS NdkGetListenerLocalAddress(
  _In_ NDK_LISTENER                                                          *pNdkListener,
       _Out_writes_bytes_to_opt_(*pAddressLength, *pAddressLength) PSOCKADDR pAddress,
       _Inout_ ULONG                                                         *pAddressLength
)
{ ... }
````


## -parameters




### -param *pNdkListener [in]

A pointer to an NDK listener object (<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>).


### -param pAddress

A local address for a listener is returned in this buffer.


### -param *pAddressLength

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

<a href="..\ndkpi\nc-ndkpi-ndk_fn_listen.md">NDK_FN_LISTEN</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>



 

 


