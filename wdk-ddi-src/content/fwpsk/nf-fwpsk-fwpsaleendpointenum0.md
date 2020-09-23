---
UID: NF:fwpsk.FwpsAleEndpointEnum0
title: FwpsAleEndpointEnum0 function (fwpsk.h)
description: The FwpsAleEndpointEnum0 function enumerates application layer enforcement (ALE) endpoints.Note  FwpsAleEndpointEnum0 is a specific version of FwpsAleEndpointEnum.
old-location: netvista\fwpsaleendpointenum0.htm
tech.root: netvista
ms.assetid: 8b3257ea-9eeb-426b-8c82-a4f0242861a8
ms.date: 05/02/2018
keywords: ["FwpsAleEndpointEnum0 function"]
ms.keywords: FwpsAleEndpointEnum0, FwpsAleEndpointEnum0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointEnum0, netvista.fwpsaleendpointenum0, wfp_ref_2_funct_3_fwps_A-B_daf596f9-09c1-4e1c-8869-8c6aec4da6cd.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsAleEndpointEnum0
 - fwpsk/FwpsAleEndpointEnum0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsAleEndpointEnum0
---

# FwpsAleEndpointEnum0 function


## -description

The 
  <b>FwpsAleEndpointEnum0</b> function enumerates application layer enforcement (ALE) endpoints.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointEnum0</b> is a specific version of <b>FwpsAleEndpointEnum</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param engineHandle 

[in]
The handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a>.

### -param enumHandle 

[in]
The enumeration handle created by a previous call to 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointdestroyenumhandle0">FwpsAleEndpointDestroyEnumHandle0</a>.

### -param numEntriesRequested 

[in]
The maximum number of endpoint property entries to return. The actual number of entries enumerated
     is returned in 
     <i>numEntriesReturned</i>. The actual number is less than the requested number only if fewer endpoints
     than the requested are present.

### -param entries 

[out]
A pointer to an array of 
     <a href="/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_ale_endpoint_properties0_">FWPS_ALE_ENDPOINT_PROPERTIES0</a> structure pointers. Each structure contains the properties of a
     single endpoint. The array contains as many elements as the value returned in 
     <i>numEntriesReturned</i>.

### -param numEntriesReturned 

[out]
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
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointcreateenumhandle0">FwpsAleEndpointCreateEnumHandle0</a>. The handle returned is associated with any parameters specified
    in the optional 
    <i>enumTemplate</i> parameter of 
    <b>FwpsAleEndpointCreateEnumHandle0</b>.

After obtaining a handle, the callout driver can call 
    <b>FwpsAleEndpointEnum0</b> to get information about the endpoints that match the enumeration parameters
    of the handle.

When finished examining endpoint properties, the callout driver must call 
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointdestroyenumhandle0">FwpsAleEndpointDestroyEnumHandle0</a> to release the system resources associated with the enumeration
    handle.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointcreateenumhandle0">
   FwpsAleEndpointCreateEnumHandle0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointdestroyenumhandle0">
   FwpsAleEndpointDestroyEnumHandle0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointgetbyid0">FwpsAleEndpointGetById0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointgetsecurityinfo0">
   FwpsAleEndpointGetSecurityInfo0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointsetsecurityinfo0">
   FwpsAleEndpointSetSecurityInfo0</a>