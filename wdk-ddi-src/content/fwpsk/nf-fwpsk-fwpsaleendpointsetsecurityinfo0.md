---
UID: NF:fwpsk.FwpsAleEndpointSetSecurityInfo0
title: FwpsAleEndpointSetSecurityInfo0 function
author: windows-driver-content
description: The FwpsAleEndpointSetSecurityInfo0 function sets security information about the application layer enforcement (ALE) endpoint enumeration session.Note  FwpsAleEndpointSetSecurityInfo0 is a specific version of FwpsAleEndpointSetSecurityInfo.
old-location: netvista\fwpsaleendpointsetsecurityinfo0.htm
old-project: netvista
ms.assetid: 7b7fed83-dcf8-466d-8bd7-42a5ed15cced
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FwpsAleEndpointSetSecurityInfo0, FwpsAleEndpointSetSecurityInfo0 function [Network Drivers Starting with Windows Vista], wfp_ref_2_funct_3_fwps_A-B_7999c73b-ee7d-4a54-b279-8a691a99d94d.xml, netvista.fwpsaleendpointsetsecurityinfo0, fwpsk/FwpsAleEndpointSetSecurityInfo0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsAleEndpointSetSecurityInfo0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsAleEndpointSetSecurityInfo0 function


## -description


The 
  <b>FwpsAleEndpointSetSecurityInfo0</b> function sets security information about the application layer
  enforcement (ALE) endpoint enumeration session.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointSetSecurityInfo0</b> is a specific version of <b>FwpsAleEndpointSetSecurityInfo</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsAleEndpointSetSecurityInfo0(
  _In_           HANDLE               engineHandle,
  _In_           SECURITY_INFORMATION securityInfo,
  _In_opt_ const SID                  *sidOwner,
  _In_opt_ const SID                  *sidGroup,
  _In_opt_ const ACL                  *dacl,
  _In_opt_ const ACL                  *sacl
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


### -param sidOwner [in, optional]

The security identifier of the security owner.


### -param sidGroup [in, optional]

The security identifier of the security group.


### -param dacl [in, optional]

The discretionary access control list.


### -param sacl [in, optional]

The system access control list.


## -returns



The 
     <b>FwpsAleEndpointSetSecurityInfo0</b> function returns one of the following NTSTATUS codes.

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

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointgetbyid0.md">FwpsAleEndpointGetById0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointenum0.md">FwpsAleEndpointEnum0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointgetsecurityinfo0.md">
   FwpsAleEndpointGetSecurityInfo0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAleEndpointSetSecurityInfo0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

