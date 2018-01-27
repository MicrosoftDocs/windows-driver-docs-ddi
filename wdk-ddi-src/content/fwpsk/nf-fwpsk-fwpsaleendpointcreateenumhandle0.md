---
UID: NF:fwpsk.FwpsAleEndpointCreateEnumHandle0
title: FwpsAleEndpointCreateEnumHandle0 function
author: windows-driver-content
description: The FwpsAleEndpointCreateEnumHandle0 function creates a handle that can be used with other application layer enforcement (ALE) endpoint functions to enumerate endpoint data.Note  FwpsAleEndpointCreateEnumHandle0 is a specific version of FwpsAleEndpointCreateEnumHandle. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. 
old-location: netvista\fwpsaleendpointcreateenumhandle0.htm
old-project: netvista
ms.assetid: 5daa3dd4-e499-4a72-b784-8a0e1ef3e92b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: fwpsk/FwpsAleEndpointCreateEnumHandle0, FwpsAleEndpointCreateEnumHandle0 function [Network Drivers Starting with Windows Vista], netvista.fwpsaleendpointcreateenumhandle0, FwpsAleEndpointCreateEnumHandle0, wfp_ref_2_funct_3_fwps_A-B_dfe65638-187e-4966-b8dc-20fac02ea7cb.xml
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
-	FwpsAleEndpointCreateEnumHandle0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsAleEndpointCreateEnumHandle0 function


## -description


The 
  <b>FwpsAleEndpointCreateEnumHandle0</b> function creates a handle that can be used with other application layer enforcement (ALE) endpoint
  functions to enumerate endpoint data.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointCreateEnumHandle0</b> is a specific version of <b>FwpsAleEndpointCreateEnumHandle</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsAleEndpointCreateEnumHandle0(
  _In_           HANDLE                           engineHandle,
  _In_opt_ const FWPS_ALE_ENDPOINT_ENUM_TEMPLATE0 *enumTemplate,
  _Out_          HANDLE                           *enumHandle
);
````


## -parameters




### -param engineHandle [in]

Handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>.


### -param enumTemplate [in, optional]

A pointer to an 
     <mshelp:link keywords="netvista.fwps_ale_endpoint_enum_template0" tabindex="0"><b>
     FWPS_ALE_ENDPOINT_ENUM_TEMPLATE0</b></mshelp:link> structure that contains parameters to narrow the endpoint
     enumeration results.


### -param enumHandle [out]

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
    <mshelp:link keywords="netvista.fwpsaleendpointdestroyenumhandle0" tabindex="0"><b>
    FwpsAleEndpointDestroyEnumHandle0</b></mshelp:link>.



## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointenum0.md">FwpsAleEndpointEnum0</a>

<mshelp:link keywords="netvista.fwpsaleendpointdestroyenumhandle0" tabindex="0"><b>
   FwpsAleEndpointDestroyEnumHandle0</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAleEndpointCreateEnumHandle0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

