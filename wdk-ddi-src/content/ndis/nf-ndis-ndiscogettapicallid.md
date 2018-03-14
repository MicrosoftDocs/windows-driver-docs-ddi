---
UID: NF:ndis.NdisCoGetTapiCallId
title: NdisCoGetTapiCallId function
author: windows-driver-content
description: NdisCoGetTapiCallId retrieves a string that TAPI applications can use to identify a particular NDIS virtual connection (VC).
old-location: netvista\ndiscogettapicallid.htm
old-project: netvista
ms.assetid: 3cb47545-177f-46ef-aff6-33ad8c9a6974
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisCoGetTapiCallId, NdisCoGetTapiCallId function [Network Drivers Starting with Windows Vista], condis_protocol_ref_97e82564-7f8b-42ba-9eda-75842f326c52.xml, ndis/NdisCoGetTapiCallId, netvista.ndiscogettapicallid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCoGetTapiCallId (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCoGetTapiCallId (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Connection_Function
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
-	NdisCoGetTapiCallId
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCoGetTapiCallId function


## -description


<b>NdisCoGetTapiCallId</b> retrieves a string that TAPI applications can use to identify a particular NDIS
  virtual connection (VC).


## -syntax


````
NDIS_STATUS NdisCoGetTapiCallId(
  _In_    NDIS_HANDLE NdisVcHandle,
  _Inout_ PVAR_STRING TapiCallId
);
````


## -parameters




### -param NdisVcHandle [in]

Specifies the NDIS handle to the VC. This handle was supplied by NDIS when the VC was originally
     created with the 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> function.


### -param TapiCallId [in, out]

Pointer to a caller-allocated buffer that receives a data structure of type VAR_STRING. Upon
     successful return, this structure describes a string that TAPI applications can use to identify the
     VC.


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
NDIS successfully returned a string identifier for the VC.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The 
       <b>ulTotalSize</b> member of the VAR_STRING structure specifies that the size of the buffer is not
       large enough to hold the string that identifies the VC. 
       <b>NdisCoGetTapiCallId</b> sets the 
       <b>ulNeededSize</b> member of the VAR_STRING structure to the required size in bytes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The handle to the VC specified by 
       <i>NdisVcHandle</i> is not valid.

</td>
</tr>
</table>
 




## -remarks



Suppose a call manager calls 
    <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> to create a VC for a TAPI
    call. NDIS in turn supplies the handle to the VC to a client. The client passes this VC handle in a call
    to the 
    <b>NdisCoGetTapiCallId</b> function to retrieve a string that identifies the VC. The client can pass this
    string identifier to a TAPI application to identify the VC.

The client creates a context for each VC that it manages. The client uses 
    <b>NdisCoGetTapiCallId</b> to retrieve a string identifier for each VC. The client passes each string
    identifier to a TAPI application to identify each VC. Later, if a TAPI application passes one of these
    string identifiers down to the client in a VC-related operation, the client must pass this string
    identifier as a Unicode string in a call to 
    <a href="..\ndis\nf-ndis-ndisclgetprotocolvccontextfromtapicallid.md">
    NdisClGetProtocolVcContextFromTapiCallId</a> to get back the correct context for the VC.

For more information about the VAR_STRING structure, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564235">TAPI Objects</a>.




## -see-also

<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>



<a href="..\ndis\nf-ndis-ndisclgetprotocolvccontextfromtapicallid.md">
   NdisClGetProtocolVcContextFromTapiCallId</a>



 

 


