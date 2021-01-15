---
UID: NC:ndkpi.NDK_FN_GET_LOCAL_ADDRESS
title: NDK_FN_GET_LOCAL_ADDRESS (ndkpi.h)
description: The NdkGetLocalAddress (NDK_FN_GET_LOCAL_ADDRESS) function returns the local address for an NDK connection.
old-location: netvista\ndk_fn_get_local_address.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_FN_GET_LOCAL_ADDRESS callback function"]
ms.keywords: NDK_FN_GET_LOCAL_ADDRESS, NDK_FN_GET_LOCAL_ADDRESS callback, NdkGetLocalAddress, NdkGetLocalAddress callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetLocalAddress, netvista.ndk_fn_get_local_address
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NDK_FN_GET_LOCAL_ADDRESS
 - ndkpi/NDK_FN_GET_LOCAL_ADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NDK_FN_GET_LOCAL_ADDRESS
---

# NDK_FN_GET_LOCAL_ADDRESS callback function


## -description

The <i>NdkGetLocalAddress</i> (<i>NDK_FN_GET_LOCAL_ADDRESS</i>) function returns the local address for an NDK connection.

## -parameters

### -param pNdkConnector 

[in]
A pointer to an NDK connector object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>).

### -param pAddress

A local address for a listener is returned in this buffer.

### -param pAddressLength

The size, in bytes, of the address buffer for input, and the size, in bytes,  of the  address written into the buffer for output.

## -returns

The 
     <i>NdkGetLocalAddress</i> function returns one of the following NTSTATUS codes.

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
The local address was written to the buffer in the <i>pAddress</i> parameter.

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

<i>NdkGetLocalAddress</i> returns the local address for a connection.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>

