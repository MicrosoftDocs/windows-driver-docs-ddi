---
UID: NC:ndkpi.NDK_FN_GET_CONNECTION_DATA
title: NDK_FN_GET_CONNECTION_DATA
author: windows-driver-content
description: The NdkGetConnectionData (NDK_FN_GET_CONNECTION_DATA) function gets read limit values and the private data sent by the peer.
old-location: netvista\ndk_fn_get_connection_data.htm
old-project: netvista
ms.assetid: A6099DCB-7F10-4BDB-B463-422C2B7A2B3F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_FN_GET_CONNECTION_DATA, NdkGetConnectionData, NdkGetConnectionData callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkGetConnectionData, netvista.ndk_fn_get_connection_data
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
-	NdkGetConnectionData
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_GET_CONNECTION_DATA callback


## -description


The <i>NdkGetConnectionData</i>  (<i>NDK_FN_GET_CONNECTION_DATA</i>) function gets read limit values and the private data sent by the peer.


## -prototype


````
NDK_FN_GET_CONNECTION_DATA NdkGetConnectionData;

NTSTATUS NdkGetConnectionData(
  _In_      NDK_CONNECTOR                                                             *pNdkConnector,
  _Out_opt_ ULONG                                                                     *pInboundReadLimit,
  _Out_opt_ ULONG                                                                     *pOutboundReadLimit,
            _Out_writes_bytes_to_opt_(*pPrivateDataLength, *pPrivateDataLength) PVOID pPrivateData,
            _Inout_ ULONG                                                             *pPrivateDataLength
)
{ ... }
````


## -parameters




### -param *pNdkConnector [in]

A pointer to an NDK connector object (<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>).


### -param *pInboundReadLimit [out, optional]

The maximum number of incoming in-progress read operations to allow on the QP is returned in this location.


### -param *pOutboundReadLimit [out, optional]

The maximum number of outgoing in-progress read operations to allow on the QP is returned in this location.


### -param pPrivateData

A pointer to private data that is returned.




### -param *pPrivateDataLength

The length, in bytes, of the private data that is provided in the <i>pPrivateData</i> parameter.

<div class="alert"><b>Note</b>  The output value does not indicate the actual length of private data stored in the buffer. NDK consumers must negotiate the format and length of the actual private data. For more information about private data, see the Remarks section.</div>
<div> </div>

## -returns



The <i>NdkGetConnectionData</i> function returns one of the following NTSTATUS codes.

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
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The value in the <i>*pPrivateDataLength</i> parameter specified a buffer size that was too small to hold the connection private data. <i>*pPrivateDataLength</i> is updated with the required size.

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



The <i>NdkGetConnectionData</i>   function gets the private data sent by the peer with connect, accept, or reject requests and the effective inbound and outbound read limit values. These values are derived from the local and remote peers' requested values and the provider's maximum limits.

To access the private data and the effective inbound read limit (IRD) and outbound read limit (ORD) values from the active side, an NDK consumer can call <i>NdkGetConnectionData</i> for a connector object that was  passed to the <a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a> function.   

To access the private data and effective IRD and ORD values from the passive side, the consumer can call <i>NdkGetConnectionData</i> for a connector object for which <a href="..\ndkpi\nc-ndkpi-ndk_fn_connect.md">NDK_FN_CONNECT</a> or  <a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_with_shared_endpoint.md">NDK_FN_CONNECT_WITH_SHARED_ENDPOINT</a> completed successfully An NDK consumer will not call this function after it calls the <a href="..\ndkpi\nc-ndkpi-ndk_fn_accept.md">NDK_FN_ACCEPT</a> function on the passive side or the <a href="..\ndkpi\nc-ndkpi-ndk_fn_complete_connect.md">NDK_FN_COMPLETE_CONNECT</a> function  on the active side.


If  the <i>pPrivateData</i> parameter  is NULL and <i>*pPrivateDataLength</i> is zero, an NDK provider must return STATUS_SUCCESS and store the required private data buffer size (<i>RDS</i>) in <i>*pPrivateDataLength</i>. 

<div class="alert"><b>Note</b>  The <i>required private data buffer size</i> (<i>RDS</i>) does not  indicate that the peer has sent that much private data. The  NDK consumer must, on both ends, have a common scheme to allow the receiving end to determine if  there is any private data or not in the private data buffer. The <i>RDS</i> might be different for each connection. 
</div>
<div> </div>
If <i>pPrivateData</i> is NULL and <i>*pPrivateDataLength</i> is greater than zero, this is an invalid request. A consumer must never do this.


If <i>pPrivateData</i> is not NULL, the provider must copy the private data to the buffer at  <i>pPrivateData</i> up to the smaller of <i>*pPrivateDataLength</i> or <i>RDS</i> in  bytes. 

If <i>*pPrivateDataLength</i> is greater than or equal to <i>RDS</i>, the provider must return STATUS_SUCCESS. Otherwise, the provider must return STATUS_BUFFER_TOO_SMALL. In both cases, the provider must store the <i>RDS</i> in <i>*pPrivateDataLength</i> before returning.  





## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_connector_dispatch.md">NDK_CONNECTOR_DISPATCH</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>



 

 


