---
UID: NF:fwpmk.FwpmEngineOpen0
title: FwpmEngineOpen0 function (fwpmk.h)
description: The FwpmEngineOpen0 function opens a session to the filter engine.Note  FwpmEngineOpen0 is a specific version of FwpmEngineOpen.
old-location: netvista\fwpmengineopen0.htm
tech.root: netvista
ms.assetid: 4d805ffe-7cf9-4cbc-9077-e191ddc24ecd
ms.date: 05/02/2018
keywords: ["FwpmEngineOpen0 function"]
ms.keywords: FwpmEngineOpen0, FwpmEngineOpen0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmEngineOpen0, netvista.fwpmengineopen0, wfp_ref_2_funct_2_fwpm_29969a12-e73c-4b61-b940-e0da4b0be737.xml
f1_keywords:
 - "fwpmk/FwpmEngineOpen0"
req.header: fwpmk.h
req.include-header: Fwpmk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
- FwpmEngineOpen0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpmEngineOpen0 function


## -description


The 
  <b>FwpmEngineOpen0</b> function opens a session to the filter engine.
<div class="alert"><b>Note</b>  <b>FwpmEngineOpen0</b> is a specific version of <b>FwpmEngineOpen</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param serverName [in, optional]

A pointer to a NULL-terminated string that specifies the standard DNS name of the system on which
     the session to the filter engine is opened. Callout drivers must specify <b>NULL</b> for this parameter.


### -param authnService [in]

The authentication service to use. For a list of valid choices for this parameter, see
     Authentication-Service Constants in the RPC section in the Microsoft Windows SDK documentation. Callout
     drivers must specify either RPC_C_AUTHN_WINNT or RPC_C_AUTHN_DEFAULT for this parameter.


### -param authIdentity [in, optional]

A pointer to a <b>SEC_WINNT_AUTH_IDENTITY_W</b> structure that contains the authentication and
     authorization credentials for accessing the filter engine. This parameter is ignored when the 
     <b>FwpmEngineOpen0</b> function is called from a callout driver. Callout drivers should set this
     parameter to <b>NULL</b>.


### -param session [in, optional]

A pointer to an 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550083(v=vs.85)">FWPM_SESSION0</a> structure that defines
     session-specific parameters for the session being opened. This pointer is optional and can be
     <b>NULL</b>.


### -param engineHandle [out]

A pointer to a variable that receives a handle for the open session to the filter engine.


## -returns



The 
     <b>FwpmEngineOpen0</b> function returns one of the following NTSTATUS codes.

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
A session to the filter engine was successfully opened. The variable pointed to by the 
       <i>engineHandle</i> parameter contains a handle for the open session.

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



A callout driver calls the 
    <b>FwpmEngineOpen0</b> function to open a session to the filter engine. A handle to an open session to the
    filter engine is a required parameter to most of the <a href="https://docs.microsoft.com/windows/desktop/FWP/windows-filtering-platform-start-page">Windows Filtering Platform</a>
<a href="https://answers.microsoft.com/windows/forum/windows_xp-performance/computer-management-storage-disk-management/f93a4e9b-5516-4e5c-9cd3-f04453ec963f"> management functions</a>.

Callout drivers normally do not need to open a session to the filter engine because callout drivers
    typically do not call any of the <a href="https://docs.microsoft.com/windows/desktop/FWP/windows-filtering-platform-start-page">Windows Filtering Platform</a> management functions.

For a callout driver to successfully open a session to the filter engine, the filter engine
    must be currently running at the time that the callout driver calls the 
    <b>FwpmEngineOpen0</b> function. A callout driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateget0">FwpmBfeStateGet0</a> function to obtain the
    current state of the filter engine. Before calling <b>FwpmBfeStateGet0</b>, the callout driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0">FwpmBfeStateSubscribeChanges0</a> function to register a callback function that will be called whenever
    there is a change in the state of the filter engine.

After a callout driver has finished accessing the filter engine, it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineclose0">FwpmEngineClose0</a> function to close the
    open session to the filter engine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateget0">FwpmBfeStateGet0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0">
   FwpmBfeStateSubscribeChanges0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutadd0">FwpmCalloutAdd0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutdeletebyid0">FwpmCalloutDeleteById0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutdeletebykey0">FwpmCalloutDeleteByKey0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineclose0">FwpmEngineClose0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/calling-other-windows-filtering-platform-functions">Other Windows Filtering
   Platform Functions</a>
 

 

