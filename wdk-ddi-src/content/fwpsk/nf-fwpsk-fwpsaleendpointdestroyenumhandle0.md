---
UID: NF:fwpsk.FwpsAleEndpointDestroyEnumHandle0
title: FwpsAleEndpointDestroyEnumHandle0 function (fwpsk.h)
description: The FwpsAleEndpointDestroyEnumHandle0 function destroys an endpoint enumeration handle that was created by calling FwpsAleEndpointCreateEnumHandle0.Note  FwpsAleEndpointDestroyEnumHandle0 is a specific version of FwpsAleEndpointDestroyEnumHandle.
old-location: netvista\fwpsaleendpointdestroyenumhandle0.htm
tech.root: netvista
ms.assetid: 45ec429e-d324-40c9-bedc-acd75ccb160e
ms.date: 05/02/2018
ms.keywords: FwpsAleEndpointDestroyEnumHandle0, FwpsAleEndpointDestroyEnumHandle0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointDestroyEnumHandle0, netvista.fwpsaleendpointdestroyenumhandle0, wfp_ref_2_funct_3_fwps_A-B_3230abaf-8185-43b4-b46f-b1c1688ede2d.xml
ms.topic: function
f1_keywords:
 - "fwpsk/FwpsAleEndpointDestroyEnumHandle0"
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
- FwpsAleEndpointDestroyEnumHandle0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsAleEndpointDestroyEnumHandle0 function


## -description


The 
  <b>FwpsAleEndpointDestroyEnumHandle0</b> function destroys an endpoint enumeration handle that was created
  by calling 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointcreateenumhandle0">
  FwpsAleEndpointCreateEnumHandle0</a>.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointDestroyEnumHandle0</b> is a specific version of <b>FwpsAleEndpointDestroyEnumHandle</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param engineHandle [in]

The handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a>.


### -param enumHandle [in, out]

The enumeration handle created by a previous call to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointcreateenumhandle0">
     FwpsAleEndpointCreateEnumHandle0</a>.


## -returns



The 
     <b>FwpsAleEndpointDestroyEnumHandle0</b> function returns one of the following NTSTATUS codes.

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



When endpoint enumeration is complete, the enumeration handle must be destroyed by calling 
    <b>FwpsAleEndpointDestroyEnumHandle0</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointcreateenumhandle0">
     FwpsAleEndpointCreateEnumHandle0</a>
 

 

