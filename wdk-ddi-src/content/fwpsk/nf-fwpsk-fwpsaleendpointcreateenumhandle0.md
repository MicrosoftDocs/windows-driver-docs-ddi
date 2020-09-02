---
UID: NF:fwpsk.FwpsAleEndpointCreateEnumHandle0
title: FwpsAleEndpointCreateEnumHandle0 function (fwpsk.h)
description: The FwpsAleEndpointCreateEnumHandle0 function creates a handle that can be used with other application layer enforcement (ALE) endpoint functions to enumerate endpoint data.Note  FwpsAleEndpointCreateEnumHandle0 is a specific version of FwpsAleEndpointCreateEnumHandle. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsaleendpointcreateenumhandle0.htm
tech.root: netvista
ms.assetid: 5daa3dd4-e499-4a72-b784-8a0e1ef3e92b
ms.date: 05/02/2018
keywords: ["FwpsAleEndpointCreateEnumHandle0 function"]
ms.keywords: FwpsAleEndpointCreateEnumHandle0, FwpsAleEndpointCreateEnumHandle0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointCreateEnumHandle0, netvista.fwpsaleendpointcreateenumhandle0, wfp_ref_2_funct_3_fwps_A-B_dfe65638-187e-4966-b8dc-20fac02ea7cb.xml
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
 - FwpsAleEndpointCreateEnumHandle0
 - fwpsk/FwpsAleEndpointCreateEnumHandle0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsAleEndpointCreateEnumHandle0
---

# FwpsAleEndpointCreateEnumHandle0 function


## -description

The 
  <b>FwpsAleEndpointCreateEnumHandle0</b> function creates a handle that can be used with other application layer enforcement (ALE) endpoint
  functions to enumerate endpoint data.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointCreateEnumHandle0</b> is a specific version of <b>FwpsAleEndpointCreateEnumHandle</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param engineHandle 

[in]
Handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a>.

### -param enumTemplate 

[in, optional]
A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_ale_endpoint_enum_template0_">
     FWPS_ALE_ENDPOINT_ENUM_TEMPLATE0</a> structure that contains parameters to narrow the endpoint
     enumeration results.

### -param enumHandle 

[out]
The newly created enumeration handle.

## -returns

The 
     <b>FwpsAleEndpointCreateEnumHandle0</b> function returns one of the following NTSTATUS codes.

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

After using the handle acquired by calling 
    <b>FwpsAleEndpointCreateEnumHandle0</b>, the callout driver must release the system resources associated
    with the handle by calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointdestroyenumhandle0">
    FwpsAleEndpointDestroyEnumHandle0</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointdestroyenumhandle0">
   FwpsAleEndpointDestroyEnumHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointenum0">FwpsAleEndpointEnum0</a>

