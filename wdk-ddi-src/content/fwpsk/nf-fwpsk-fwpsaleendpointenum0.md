---
UID: NF:fwpsk.FwpsAleEndpointEnum0
title: FwpsAleEndpointEnum0 function
author: windows-driver-content
description: The FwpsAleEndpointEnum0 function enumerates application layer enforcement (ALE) endpoints.Note  FwpsAleEndpointEnum0 is a specific version of FwpsAleEndpointEnum.
old-location: netvista\fwpsaleendpointenum0.htm
old-project: netvista
ms.assetid: 8b3257ea-9eeb-426b-8c82-a4f0242861a8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FwpsAleEndpointEnum0, FwpsAleEndpointEnum0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointEnum0, netvista.fwpsaleendpointenum0, wfp_ref_2_funct_3_fwps_A-B_daf596f9-09c1-4e1c-8869-8c6aec4da6cd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsAleEndpointEnum0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsAleEndpointEnum0 function


## -description


The 
  <b>FwpsAleEndpointEnum0</b> function enumerates application layer enforcement (ALE) endpoints.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointEnum0</b> is a specific version of <b>FwpsAleEndpointEnum</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param engineHandle [in]

The handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550075">FwpmEngineOpen0</a>.


### -param enumHandle [in]

The enumeration handle created by a previous call to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550091">FwpsAleEndpointDestroyEnumHandle0</a>.


### -param numEntriesRequested [in]

The maximum number of endpoint property entries to return. The actual number of entries enumerated
     is returned in 
     <i>numEntriesReturned</i>. The actual number is less than the requested number only if fewer endpoints
     than the requested are present.


### -param entries [out]

A pointer to an array of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551218">FWPS_ALE_ENDPOINT_PROPERTIES0</a> structure pointers. Each structure contains the properties of a
     single endpoint. The array contains as many elements as the value returned in 
     <i>numEntriesReturned</i>.


### -param numEntriesReturned [out]

On return, the number of elements in the array of endpoint property structures pointed to by 
     <i>entries</i>.


## -returns



The 
     <b>FwpsAleEndpointEnum0</b> function returns one of the following NTSTATUS codes.

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
The function succeeded.

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



To enumerate ALE endpoints, the callout driver must first obtain an enumeration handle by calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff550089">FwpsAleEndpointCreateEnumHandle0</a>. The handle returned is associated with any parameters specified
    in the optional 
    <i>enumTemplate</i> parameter of 
    <b>FwpsAleEndpointCreateEnumHandle0</b>.

After obtaining a handle, the callout driver can call 
    <b>FwpsAleEndpointEnum0</b> to get information about the endpoints that match the enumeration parameters
    of the handle.

When finished examining endpoint properties, the callout driver must call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff550091">FwpsAleEndpointDestroyEnumHandle0</a> to release the system resources associated with the enumeration
    handle.




## -see-also




<a href="https://msdn.microsoft.com/5daa3dd4-e499-4a72-b784-8a0e1ef3e92b">
   FwpsAleEndpointCreateEnumHandle0</a>



<a href="https://msdn.microsoft.com/45ec429e-d324-40c9-bedc-acd75ccb160e">
   FwpsAleEndpointDestroyEnumHandle0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551128">FwpsAleEndpointGetById0</a>



<a href="https://msdn.microsoft.com/0c825695-7fef-4eb1-8615-f41c526aa32d">
   FwpsAleEndpointGetSecurityInfo0</a>



<a href="https://msdn.microsoft.com/7b7fed83-dcf8-466d-8bd7-42a5ed15cced">
   FwpsAleEndpointSetSecurityInfo0</a>
 

 

