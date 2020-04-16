---
UID: NF:fwpmk.FwpmBfeStateUnsubscribeChanges0
title: FwpmBfeStateUnsubscribeChanges0 function (fwpmk.h)
description: The FwpmBfeStateUnsubscribeChanges0 function deregisters a base filtering engine (BFE) callback function that was previously registered by calling the FwpmBfeStateSubscribeChanges0 function.Note  FwpmBfeStateUnsubscribeChanges0 is a specific version of FwpmBfeStateUnsubscribeChanges. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpmbfestateunsubscribechanges0.htm
tech.root: netvista
ms.assetid: 1a84401a-d7da-43d2-925d-0d6ed370c980
ms.date: 05/02/2018
keywords: ["FwpmBfeStateUnsubscribeChanges0 function"]
ms.keywords: FwpmBfeStateUnsubscribeChanges0, FwpmBfeStateUnsubscribeChanges0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmBfeStateUnsubscribeChanges0, netvista.fwpmbfestateunsubscribechanges0, wfp_ref_2_funct_2_fwpm_2b1f650b-81ab-4dd9-be56-97039f86ac1e.xml
f1_keywords:
 - "fwpmk/FwpmBfeStateUnsubscribeChanges0"
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
- FwpmBfeStateUnsubscribeChanges0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpmBfeStateUnsubscribeChanges0 function


## -description


The 
  <b>FwpmBfeStateUnsubscribeChanges0</b> function deregisters a base filtering engine (BFE) callback function that was previously
  registered by calling the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0">
  FwpmBfeStateSubscribeChanges0</a> function.
<div class="alert"><b>Note</b>  <b>FwpmBfeStateUnsubscribeChanges0</b> is a specific version of <b>FwpmBfeStateUnsubscribeChanges</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param changeHandle [in, out]

A handle associated with the registration of the callback function that is being deregistered.
     This handle was returned to the callout driver when it called the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0">FwpmBfeStateSubscribeChanges0</a> function to register the callback function.


## -returns



The 
     <b>FwpmBfeStateUnsubscribeChanges0</b> function returns one of the following NTSTATUS codes:

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
The callback function was successfully deregistered.

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
    <b>FwpmBfeStateUnsubscribeChanges0</b> function to deregister a callback function that was previously
    registered by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0">
    FwpmBfeStateSubscribeChanges0</a> function.

If a callout driver registers a callback function by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0">
    FwpmBfeStateSubscribeChanges0</a> function, it must deregister the callback function before the callout
    driver can be unloaded.

Do not call <b>FwpmBfeStateUnsubscribeChanges0</b> from a callback function that your driver previously registered by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0">
    FwpmBfeStateSubscribeChanges0</a>. Doing so can cause a deadlock.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0">
   FwpmBfeStateSubscribeChanges0</a>
 

 

