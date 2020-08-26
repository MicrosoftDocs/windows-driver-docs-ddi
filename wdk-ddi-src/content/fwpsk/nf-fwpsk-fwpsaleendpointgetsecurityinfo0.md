---
UID: NF:fwpsk.FwpsAleEndpointGetSecurityInfo0
title: FwpsAleEndpointGetSecurityInfo0 function (fwpsk.h)
description: The FwpsAleEndpointGetSecurityInfo0 function retrieves security information about the application layer enforcement (ALE) endpoint enumeration session.Note  FwpsAleEndpointGetSecurityInfo0 is a specific version of FwpsAleEndpointGetSecurityInfo.
old-location: netvista\fwpsaleendpointgetsecurityinfo0.htm
tech.root: netvista
ms.assetid: 0c825695-7fef-4eb1-8615-f41c526aa32d
ms.date: 05/02/2018
keywords: ["FwpsAleEndpointGetSecurityInfo0 function"]
ms.keywords: FwpsAleEndpointGetSecurityInfo0, FwpsAleEndpointGetSecurityInfo0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointGetSecurityInfo0, netvista.fwpsaleendpointgetsecurityinfo0, wfp_ref_2_funct_3_fwps_A-B_83803cc6-94be-4b32-8b33-2d12cec31e9e.xml
f1_keywords:
 - "fwpsk/FwpsAleEndpointGetSecurityInfo0"
 - "FwpsAleEndpointGetSecurityInfo0"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsAleEndpointGetSecurityInfo0
targetos: Windows
req.typenames: 
---

# FwpsAleEndpointGetSecurityInfo0 function


## -description


The 
  <b>FwpsAleEndpointGetSecurityInfo0</b> function retrieves security information about the application layer
  enforcement (ALE) endpoint enumeration session.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointGetSecurityInfo0</b> is a specific version of <b>FwpsAleEndpointGetSecurityInfo</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param engineHandle 
[in]
A handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a>.


### -param securityInfo 
[in]
A set of security information flags. For more information, see the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a> description in the
     Installable File Systems driver documentation.


### -param sidOwner 
[out]
The security identifier of the security owner.


### -param sidGroup 
[out]
The security identifier of the security group.


### -param dacl 
[out]
The discretionary access control list.


### -param sacl 
[out]
The system access control list.


### -param securityDescriptor 
[out]
The security descriptor structure.


## -returns



The 
     <b>FwpsAleEndpointGetSecurityInfo0</b> function returns one of the following NTSTATUS codes.

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointenum0">FwpsAleEndpointEnum0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointgetbyid0">FwpsAleEndpointGetById0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointsetsecurityinfo0">
   FwpsAleEndpointSetSecurityInfo0</a>
 

 

