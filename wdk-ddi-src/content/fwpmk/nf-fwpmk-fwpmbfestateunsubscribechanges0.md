---
UID: NF:fwpmk.FwpmBfeStateUnsubscribeChanges0
title: FwpmBfeStateUnsubscribeChanges0 function
author: windows-driver-content
description: The FwpmBfeStateUnsubscribeChanges0 function deregisters a base filtering engine (BFE) callback function that was previously registered by calling the FwpmBfeStateSubscribeChanges0 function.Note  FwpmBfeStateUnsubscribeChanges0 is a specific version of FwpmBfeStateUnsubscribeChanges. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpmbfestateunsubscribechanges0.htm
old-project: netvista
ms.assetid: 1a84401a-d7da-43d2-925d-0d6ed370c980
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FwpmBfeStateUnsubscribeChanges0, FwpmBfeStateUnsubscribeChanges0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmBfeStateUnsubscribeChanges0, netvista.fwpmbfestateunsubscribechanges0, wfp_ref_2_funct_2_fwpm_2b1f650b-81ab-4dd9-be56-97039f86ac1e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpmBfeStateUnsubscribeChanges0
product:
- Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# FwpmBfeStateUnsubscribeChanges0 function


## -description


The 
  <b>FwpmBfeStateUnsubscribeChanges0</b> function deregisters a base filtering engine (BFE) callback function that was previously
  registered by calling the 
  <a href="https://msdn.microsoft.com/375af8a1-9e05-4830-9074-6313b4e082d9">
  FwpmBfeStateSubscribeChanges0</a> function.
<div class="alert"><b>Note</b>  <b>FwpmBfeStateUnsubscribeChanges0</b> is a specific version of <b>FwpmBfeStateUnsubscribeChanges</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param changeHandle [in, out]

A handle associated with the registration of the callback function that is being deregistered.
     This handle was returned to the callout driver when it called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550062">FwpmBfeStateSubscribeChanges0</a> function to register the callback function.


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
    <a href="https://msdn.microsoft.com/375af8a1-9e05-4830-9074-6313b4e082d9">
    FwpmBfeStateSubscribeChanges0</a> function.

If a callout driver registers a callback function by calling the 
    <a href="https://msdn.microsoft.com/375af8a1-9e05-4830-9074-6313b4e082d9">
    FwpmBfeStateSubscribeChanges0</a> function, it must deregister the callback function before the callout
    driver can be unloaded.

Do not call <b>FwpmBfeStateUnsubscribeChanges0</b> from a callback function that your driver previously registered by calling <a href="https://msdn.microsoft.com/375af8a1-9e05-4830-9074-6313b4e082d9">
    FwpmBfeStateSubscribeChanges0</a>. Doing so can cause a deadlock.




## -see-also




<a href="https://msdn.microsoft.com/375af8a1-9e05-4830-9074-6313b4e082d9">
   FwpmBfeStateSubscribeChanges0</a>
 

 

