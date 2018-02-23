---
UID: NF:fwpmk.FwpmCalloutDeleteById0
title: FwpmCalloutDeleteById0 function
author: windows-driver-content
description: The FwpmCalloutDeleteById0 function deletes a callout from the filter engine.Note  FwpmCalloutDeleteById0 is a specific version of FwpmCalloutDeleteById.
old-location: netvista\fwpmcalloutdeletebyid0.htm
old-project: netvista
ms.assetid: fa24de4c-de78-49b1-9c8d-ca9a63c8a84f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wfp_ref_2_funct_2_fwpm_466376ac-f7a1-417e-9de8-9c3a7ff31404.xml, FwpmCalloutDeleteById0, fwpmk/FwpmCalloutDeleteById0, netvista.fwpmcalloutdeletebyid0, FwpmCalloutDeleteById0 function [Network Drivers Starting with Windows Vista]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpmCalloutDeleteById0
product: Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# FwpmCalloutDeleteById0 function


## -description


The 
  <b>FwpmCalloutDeleteById0</b> function deletes a callout from the filter engine.
<div class="alert"><b>Note</b>  <b>FwpmCalloutDeleteById0</b> is a specific version of <b>FwpmCalloutDeleteById</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpmCalloutDeleteById0(
  _In_ HANDLE engineHandle,
  _In_ UINT32 id
);
````


## -parameters




### -param engineHandle [in]

A handle for an open session to the filter engine. A callout driver calls the 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a> function to open a
     session to the filter engine.


### -param id [in]

The run-time identifier for the callout that is being deleted from the filter engine. This must be
     the run-time identifier that was returned when the callout driver called the 
     <a href="..\fwpmk\nf-fwpmk-fwpmcalloutadd0.md">FwpmCalloutAdd0</a> function to add the
     callout to the filter engine.


## -returns



The 
     <b>FwpmCalloutDeleteById0</b> function returns one of the following NTSTATUS codes.

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
There is not a callout in the filter engine that matches the run-time identifier specified in
       the 
       <i>id</i> parameter.

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
    <b>FwpmCalloutDeleteById0</b> function to delete a callout from the filter engine, using the run-time
    identifier to identify the callout to be deleted.

Callout drivers do not typically delete their callouts from the filter engine. In most situations, this
    is handled by a user-mode <a href="https://msdn.microsoft.com/0436f559-20e6-4199-8391-10eb7d85df23">Windows Filtering Platform</a> management application.

A callout can be deleted from the filter engine only if there are no filters in the filter engine that
    specify the callout for the filter's action.




## -see-also

<a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>



<a href="..\fwpmk\nf-fwpmk-fwpmcalloutdeletebykey0.md">FwpmCalloutDeleteByKey0</a>



<a href="..\fwpmk\nf-fwpmk-fwpmcalloutadd0.md">FwpmCalloutAdd0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpmCalloutDeleteById0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

