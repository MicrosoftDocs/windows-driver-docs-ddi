---
UID: NF:ndis.NdisClGetProtocolVcContextFromTapiCallId
title: NdisClGetProtocolVcContextFromTapiCallId function
author: windows-driver-content
description: NdisClGetProtocolVcContextFromTapiCallId retrieves the client context for a virtual connection (VC) identified by a TAPI Call ID string.
old-location: netvista\ndisclgetprotocolvccontextfromtapicallid.htm
old-project: netvista
ms.assetid: 5c716207-b093-499a-8fad-344b5ac51e25
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, G, I, N, NdisClGetProtocolVcContextFromTapiCallId, NdisClGetProtocolVcContextFromTapiCallId function [Network Drivers Starting with Windows Vista], P, T, V, a, c, condis_client_ref_0f7c98a1-306b-40b4-b84c-0e624c936e90.xml, d, e, i, l, m, n, ndis/NdisClGetProtocolVcContextFromTapiCallId, netvista.ndisclgetprotocolvccontextfromtapicallid, o, p, r, s, t, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisClGetProtocolVcContextFromTapiCallId (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1   drivers (see       NdisClGetProtocolVcContextFromTapiCallId (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisClGetProtocolVcContextFromTapiCallId
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisClGetProtocolVcContextFromTapiCallId function


## -description


<b>NdisClGetProtocolVcContextFromTapiCallId</b> retrieves the client context for a virtual connection (VC)
  identified by a TAPI Call ID string.


## -syntax


````
NDIS_STATUS NdisClGetProtocolVcContextFromTapiCallId(
  _In_  UNICODE_STRING TapiCallId,
  _Out_ PNDIS_HANDLE   ProtocolVcContext
);
````


## -parameters




### -param TapiCallId [in]

Unicode string that identifies a particular VC. This string is the Unicode version of a string
     identifier that was previously returned by the 
     <a href="..\ndis\nf-ndis-ndiscogettapicallid.md">NdisCoGetTapiCallID</a> function.


### -param ProtocolVcContext [out]

Pointer to a caller-allocated NDIS_HANDLE that receives a handle to the client context for the VC.
     The client supplied this context to NDIS on return from its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> handler.


## -returns



Returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NDIS successfully retrieved the handle to the client VC context for the VC identified by the
       TAPI Call ID string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The attempt to retrieve the handle to the client VC context failed.

</td>
</tr>
</table>
 




## -remarks



Suppose a call manager calls 
    <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> to create a VC for a TAPI
    call. NDIS in turn supplies the handle to the VC to a client. The client passes this VC handle in a call
    to the 
    <a href="..\ndis\nf-ndis-ndiscogettapicallid.md">NdisCoGetTapiCallId</a> function to
    retrieve a string identifier for the VC. The client can then present this identifier as a Unicode string
    to 
    <b>NdisClGetProtocolVcContextFromTapiCallId</b> to get back its context for the VC.

The client creates a context for each VC that it manages. The client uses 
    <b>NdisCoGetTapiCallId</b> to retrieve a string identifier for each VC. The client passes each string
    identifier to a TAPI application to identify each VC. Later, if a TAPI application passes one of these
    string identifiers down to the client in a VC-related operation, the client must pass this string
    identifier as a Unicode string in a call to 
    <b>NdisClGetProtocolVcContextFromTapiCallId</b> to get back the correct context for the VC.

See the 
    <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure for more
    information.




## -see-also

<a href="..\ndis\nf-ndis-ndiscogettapicallid.md">NdisCoGetTapiCallId</a>



<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisClGetProtocolVcContextFromTapiCallId function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

