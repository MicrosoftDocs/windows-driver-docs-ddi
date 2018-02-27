---
UID: NC:ndkpi.NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS
title: NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS
author: windows-driver-content
description: The NdkGetSharedEndpointLocalAddress (NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS) function returns the local address for an NDK shared endpoint.
old-location: netvista\ndk_fn_get_shared_endpoint_local_address.htm
old-project: netvista
ms.assetid: C7B6B7DC-359D-44C2-8348-EC1EE5965800
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS, NdkGetSharedEndpointLocalAddress, NdkGetSharedEndpointLocalAddress callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetSharedEndpointLocalAddress, netvista.ndk_fn_get_shared_endpoint_local_address
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndkpi.h
apiname:
-	NdkGetSharedEndpointLocalAddress
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS callback


## -description


The <i>NdkGetSharedEndpointLocalAddress</i> (<i>NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS</i>) function returns the local address for an NDK  shared endpoint.


## -prototype


````
NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS NdkGetSharedEndpointLocalAddress;

NTSTATUS NdkGetSharedEndpointLocalAddress(
  _In_ NDK_SHARED_ENDPOINT                                                   *pNdkSharedEndpoint,
       _Out_writes_bytes_to_opt_(*pAddressLength, *pAddressLength) PSOCKADDR pAddress,
       _Inout_ ULONG                                                         *pAddressLength
)
{ ... }
````


## -parameters




### -param *pNdkSharedEndpoint [in]

A pointer to an NDK shared endpoint object  (<a href="..\ndkpi\ns-ndkpi-_ndk_shared_endpoint.md">NDK_SHARED_ENDPOINT</a>).


### -param pAddress

A local address is returned in this buffer.


### -param *pAddressLength

The size, in bytes, of the address buffer for input, and the size, in bytes, of the actual address written into the buffer for output.


## -returns



The 
     <i>NdkGetSharedEndpointLocalAddress</i> function returns one of the following NTSTATUS codes.

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



<i>NdkGetSharedEndpointLocalAddress</i> returns the local address for a shared endpoint. <i>NdkGetSharedEndpointLocalAddress</i> retrieves port information for an AF_INET or AF_INET6  shared endpoint. That is, if the NDK consumer specifies zero as the ND port number in a shared endpoint creation request, the NDK provider picks a port. An NDK consumer can determine the port that the provider picked with <i>NdkGetSharedEndpointLocalAddress</i>.




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_shared_endpoint.md">NDK_SHARED_ENDPOINT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

