---
UID: NF:fwpsk.FwpsFlowAbort0
title: FwpsFlowAbort0 function
author: windows-driver-content
description: The FwpsFlowAbort0 function aborts a data flow.Note  FwpsFlowAbort0 is a specific version of FwpsFlowAbort.
old-location: netvista\fwpsflowabort0.htm
old-project: netvista
ms.assetid: 029dd387-498f-4402-9e61-a46688294949
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FwpsFlowAbort0, FwpsFlowAbort0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsFlowAbort0, netvista.fwpsflowabort0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsFlowAbort0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsFlowAbort0 function


## -description


The <b>FwpsFlowAbort0</b> function aborts a data flow.<div class="alert"><b>Note</b>  <b>FwpsFlowAbort0</b> is a specific version of <b>FwpsFlowAbort</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param flowId [in]

A run-time identifier that specifies the data flow that is being aborted. The run-time identifier for a data flow is provided to a callout driver through the FWPS_METADATA_FIELD_FLOW_HANDLE metadata value that the filter engine provided to the callout driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function.




## -returns



The 
     <b>FwpsFlowAbort0</b> function returns one of the following NTSTATUS codes.

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
The flow was aborted. 

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




    A callout driver can call the <b>FwpsFlowAbort0</b> function to abort a data flow. 
   The filter engine calls the 
    <a href="https://msdn.microsoft.com/65449a23-da5d-4884-b98e-030461eb019a">flowDeleteFn</a> callout function when the flow is terminated so that the callout driver can clean up
    the context associated with the flow.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>



<a href="https://msdn.microsoft.com/65449a23-da5d-4884-b98e-030461eb019a">flowDeleteFn</a>
 

 

