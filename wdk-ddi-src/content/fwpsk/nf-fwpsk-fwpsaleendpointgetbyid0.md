---
UID: NF:fwpsk.FwpsAleEndpointGetById0
title: FwpsAleEndpointGetById0 function
author: windows-driver-content
description: The FwpsAleEndpointGetById0 function retrieves information about an application layer enforcement (ALE) endpoint.Note  FwpsAleEndpointGetById0 is a specific version of FwpsAleEndpointGetById.
old-location: netvista\fwpsaleendpointgetbyid0.htm
tech.root: netvista
ms.assetid: fa9a5078-d254-4b4a-bbfb-256491beff5f
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: FwpsAleEndpointGetById0, FwpsAleEndpointGetById0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointGetById0, netvista.fwpsaleendpointgetbyid0, wfp_ref_2_funct_3_fwps_A-B_3feb07cf-ae5a-4412-a51a-8e4d4d65c31d.xml
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
-	FwpsAleEndpointGetById0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsAleEndpointGetById0 function


## -description


The 
  <b>FwpsAleEndpointGetById0</b> function retrieves information about an application layer enforcement (ALE)
  endpoint.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointGetById0</b> is a specific version of <b>FwpsAleEndpointGetById</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param engineHandle [in]

A handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550075">FwpmEngineOpen0</a>.


### -param endpointId [in]

The unique endpoint identifier.


### -param properties [out]

A pointer to an 
     <a href="https://msdn.microsoft.com/1dd5dbd1-b7a7-45a3-8cab-ea62c7eff35b">
     FWPS_ALE_ENDPOINT_PROPERTIES0</a> structure that contains the properties of the endpoint.


## -returns



The 
     <b>FwpsAleEndpointGetById0</b> function returns one of the following NTSTATUS codes.

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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551126">FwpsAleEndpointEnum0</a>



<a href="https://msdn.microsoft.com/0c825695-7fef-4eb1-8615-f41c526aa32d">
   FwpsAleEndpointGetSecurityInfo0</a>



<a href="https://msdn.microsoft.com/7b7fed83-dcf8-466d-8bd7-42a5ed15cced">
   FwpsAleEndpointSetSecurityInfo0</a>
 

 

