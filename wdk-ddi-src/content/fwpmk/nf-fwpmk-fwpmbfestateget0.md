---
UID: NF:fwpmk.FwpmBfeStateGet0
title: FwpmBfeStateGet0 function
author: windows-driver-content
description: The FwpmBfeStateGet0 function retrieves the current state of the filter engine.Note  FwpmBfeStateGet0 is a specific version of FwpmBfeStateGet.
old-location: netvista\fwpmbfestateget0.htm
old-project: netvista
ms.assetid: f165c5a0-6f8e-495f-90b9-62d0d8982456
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpmBfeStateGet0, FwpmBfeStateGet0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmBfeStateGet0, netvista.fwpmbfestateget0, wfp_ref_2_funct_2_fwpm_6f70e48b-0c6c-465e-95c3-fa41413398db.xml
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Fwpkclnt.lib
-	Fwpkclnt.dll
api_name:
-	FwpmBfeStateGet0
product: Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# FwpmBfeStateGet0 function


## -description


The 
  <b>FwpmBfeStateGet0</b> function retrieves the current state of the filter engine.
<div class="alert"><b>Note</b>  <b>FwpmBfeStateGet0</b> is a specific version of <b>FwpmBfeStateGet</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
FWPM_SERVICE_STATE NTAPI FwpmBfeStateGet0(void);
````


## -parameters






## -returns



The 
     <b>FwpmBfeStateGet0</b> function returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FWPM_SERVICE_STOPPED</b></dt>
</dl>
</td>
<td width="60%">
The filter engine is not running.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FWPM_SERVICE_START_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The filter engine is starting.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FWPM_SERVICE_STOP_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The filter engine is stopping.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FWPM_SERVICE_RUNNING</b></dt>
</dl>
</td>
<td width="60%">
The filter engine is running.

</td>
</tr>
</table>
 




## -remarks



A callout driver calls the 
    <b>FwpmBfeStateGet0</b> function to retrieve the current state of the filter engine. For a callout driver
    to open a session to the filter engine, the filter engine must  be currently running.

Before calling <b>FwpmBfeStateGet0</b>, the callout driver  must call the 
    <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">FwpmBfeStateSubscribeChanges0</a> function to register a callback function that is called whenever the
    state of the filter engine changes.




## -see-also

<a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">
   FwpmBfeStateSubscribeChanges0</a>



 

 


