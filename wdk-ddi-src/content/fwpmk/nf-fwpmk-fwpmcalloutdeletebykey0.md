---
UID: NF:fwpmk.FwpmCalloutDeleteByKey0
title: FwpmCalloutDeleteByKey0 function
author: windows-driver-content
description: The FwpmCalloutDeleteByKey0 function deletes a callout from the filter engine.Note  FwpmCalloutDeleteByKey0 is a specific version of FwpmCalloutDeleteByKey.
old-location: netvista\fwpmcalloutdeletebykey0.htm
tech.root: netvista
ms.assetid: b4c3cb7e-9c4a-40a5-a11b-952562c4790b
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: FwpmCalloutDeleteByKey0, FwpmCalloutDeleteByKey0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmCalloutDeleteByKey0, netvista.fwpmcalloutdeletebykey0, wfp_ref_2_funct_2_fwpm_606dbd2f-8df7-497b-8feb-ba7aedbabedb.xml
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
-	FwpmCalloutDeleteByKey0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpmCalloutDeleteByKey0 function


## -description


The 
  <b>FwpmCalloutDeleteByKey0</b> function deletes a callout from the filter engine.
<div class="alert"><b>Note</b>  <b>FwpmCalloutDeleteByKey0</b> is a specific version of <b>FwpmCalloutDeleteByKey</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param engineHandle [in]

A handle for an open session to the filter engine. A callout driver calls the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550075">FwpmEngineOpen0</a> function to open a
     session to the filter engine.


### -param key [in]

A pointer to a GUID that uniquely identifies the callout that is being deleted from the filter
     engine. This must be a pointer to the same GUID that was specified when the callout driver called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550067">FwpmCalloutAdd0</a> function to add the
     callout to the filter engine.


## -returns



The 
     <b>FwpmCalloutDeleteByKey0</b> function returns one of the following NTSTATUS codes.

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
The callout was successfully deleted from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
One or more filters in the filter engine specify the callout for the filter's action.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_CALLOUT_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
There is not a callout in the filter engine that matches the GUID specified in the 
       <i>key</i> parameter.

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
    <b>FwpmCalloutDeleteByKey0</b> function to delete a callout from the filter engine, using the GUID key to
    identify the callout to be deleted.

Callout drivers do not typically delete their callouts from the filter engine. In most situations, this
    is handled by a user-mode <a href="https://msdn.microsoft.com/0436f559-20e6-4199-8391-10eb7d85df23">Windows Filtering Platform</a> management application.

A callout can be deleted from the filter engine only if there are no filters in the filter engine that
    specify the callout for the filter's action.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550067">FwpmCalloutAdd0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550069">FwpmCalloutDeleteById0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550075">FwpmEngineOpen0</a>
 

 

