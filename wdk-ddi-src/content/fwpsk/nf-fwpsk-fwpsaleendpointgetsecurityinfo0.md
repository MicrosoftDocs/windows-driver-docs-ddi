---
UID: NF:fwpsk.FwpsAleEndpointGetSecurityInfo0
title: FwpsAleEndpointGetSecurityInfo0 function
author: windows-driver-content
description: The FwpsAleEndpointGetSecurityInfo0 function retrieves security information about the application layer enforcement (ALE) endpoint enumeration session.Note  FwpsAleEndpointGetSecurityInfo0 is a specific version of FwpsAleEndpointGetSecurityInfo.
old-location: netvista\fwpsaleendpointgetsecurityinfo0.htm
old-project: netvista
ms.assetid: 0c825695-7fef-4eb1-8615-f41c526aa32d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsAleEndpointGetSecurityInfo0, FwpsAleEndpointGetSecurityInfo0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointGetSecurityInfo0, netvista.fwpsaleendpointgetsecurityinfo0, wfp_ref_2_funct_3_fwps_A-B_83803cc6-94be-4b32-8b33-2d12cec31e9e.xml
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
-	FwpsAleEndpointGetSecurityInfo0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsAleEndpointGetSecurityInfo0 function


## -description


The 
  <b>FwpsAleEndpointGetSecurityInfo0</b> function retrieves security information about the application layer
  enforcement (ALE) endpoint enumeration session.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointGetSecurityInfo0</b> is a specific version of <b>FwpsAleEndpointGetSecurityInfo</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsAleEndpointGetSecurityInfo0(
  _In_  HANDLE               engineHandle,
  _In_  SECURITY_INFORMATION securityInfo,
  _Out_ PSID                 *sidOwner,
  _Out_ PSID                 *sidGroup,
  _Out_ PACL                 *dacl,
  _Out_ PACL                 *sacl,
  _Out_ PSECURITY_DESCRIPTOR *securityDescriptor
);
````


## -parameters




### -param engineHandle [in]

A handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>.


### -param securityInfo [in]

A set of security information flags. For more information, see the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a> description in the
     Installable File Systems driver documentation.


### -param sidOwner [out]

The security identifier of the security owner.


### -param sidGroup [out]

The security identifier of the security group.


### -param dacl [out]

The discretionary access control list.


### -param sacl [out]

The system access control list.


### -param securityDescriptor [out]

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

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointsetsecurityinfo0.md">
   FwpsAleEndpointSetSecurityInfo0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointenum0.md">FwpsAleEndpointEnum0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointgetbyid0.md">FwpsAleEndpointGetById0</a>



 

 


