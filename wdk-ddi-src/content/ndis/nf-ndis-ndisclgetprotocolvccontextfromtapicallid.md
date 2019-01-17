---
UID: NF:ndis.NdisClGetProtocolVcContextFromTapiCallId
title: NdisClGetProtocolVcContextFromTapiCallId function
description: NdisClGetProtocolVcContextFromTapiCallId retrieves the client context for a virtual connection (VC) identified by a TAPI Call ID string.
old-location: netvista\ndisclgetprotocolvccontextfromtapicallid.htm
tech.root: netvista
ms.assetid: 5c716207-b093-499a-8fad-344b5ac51e25
ms.date: 05/02/2018
ms.keywords: NdisClGetProtocolVcContextFromTapiCallId, NdisClGetProtocolVcContextFromTapiCallId function [Network Drivers Starting with Windows Vista], condis_client_ref_0f7c98a1-306b-40b4-b84c-0e624c936e90.xml, ndis/NdisClGetProtocolVcContextFromTapiCallId, netvista.ndisclgetprotocolvccontextfromtapicallid
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisClGetProtocolVcContextFromTapiCallId
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisClGetProtocolVcContextFromTapiCallId function


## -description


<b>NdisClGetProtocolVcContextFromTapiCallId</b> retrieves the client context for a virtual connection (VC)
  identified by a TAPI Call ID string.


## -parameters




### -param TapiCallId [in]

Unicode string that identifies a particular VC. This string is the Unicode version of a string
     identifier that was previously returned by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561700">NdisCoGetTapiCallID</a> function.


### -param ProtocolVcContext [out]

Pointer to a caller-allocated NDIS_HANDLE that receives a handle to the client context for the VC.
     The client supplied this context to NDIS on return from its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> handler.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a> to create a VC for a TAPI
    call. NDIS in turn supplies the handle to the VC to a client. The client passes this VC handle in a call
    to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561700">NdisCoGetTapiCallId</a> function to
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure for more
    information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561700">NdisCoGetTapiCallId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

