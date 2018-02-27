---
UID: NC:ndkpi.NDK_FN_REJECT
title: NDK_FN_REJECT
author: windows-driver-content
description: The NdkReject (NDK_FN_REJECT) function rejects an incoming NDK connection request.
old-location: netvista\ndk_fn_reject.htm
old-project: netvista
ms.assetid: BBD02954-C907-4EA4-8605-EC90CC62ECB7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDK_FN_REJECT, NdkReject, NdkReject callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkReject, netvista.ndk_fn_reject
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
-	NdkReject
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_REJECT callback


## -description


The <i>NdkReject</i> (<i>NDK_FN_REJECT</i>) function rejects an incoming NDK connection request.


## -prototype


````
NDK_FN_REJECT NdkReject;

NTSTATUS NdkReject(
  _In_ NDK_CONNECTOR                                       *pNdkConnector,
       _In_reads_bytes_opt_(PrivateDataLength) CONST PVOID pPrivateData,
  _In_ ULONG                                               PrivateDataLength
)
{ ... }
````


## -parameters




### -param *pNdkConnector [in]

A pointer to an NDK connector object
(<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>).


### -param PVOID


### -param PrivateDataLength [in]

The length, in bytes, of the private data that is provided in the <i>pPrivateData</i> parameter.




#### - pPrivateData

A pointer to private data that is sent back with the reject request.




## -returns



The 
     <i>NdkReject</i> function returns one of the following NTSTATUS codes.

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
The reject request was successful.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The connecting peer abandoned the connection establishment.



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



<i>NdkReject</i> rejects an incoming connection request over a listener. A connection request can also be rejected for a connection request where the  <i>NdkConnect</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect.md">NDK_FN_CONNECT</a>) function  has been completed and the consumer rejects the connection. For example, the consumer rejects the connection because of the  values in the  <i>pInboundReadLimit</i>, <i>pOutboundReadLimit</i>, or <i>pPrivateData</i> parameters available with the <i>NdkGetConnectionData</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_connection_data.md">NDK_FN_GET_CONNECTION_DATA</a>) function.




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect.md">NDK_FN_CONNECT</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_connection_data.md">NDK_FN_GET_CONNECTION_DATA</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_connector_dispatch.md">NDK_CONNECTOR_DISPATCH</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_accept.md">NDK_FN_ACCEPT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_REJECT callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

