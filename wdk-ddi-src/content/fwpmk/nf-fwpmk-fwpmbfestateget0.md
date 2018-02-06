---
UID: NF:fwpmk.FwpmBfeStateGet0
title: FwpmBfeStateGet0 function
author: windows-driver-content
description: The FwpmBfeStateGet0 function retrieves the current state of the filter engine.Note  FwpmBfeStateGet0 is a specific version of FwpmBfeStateGet.
old-location: netvista\fwpmbfestateget0.htm
old-project: netvista
ms.assetid: f165c5a0-6f8e-495f-90b9-62d0d8982456
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: fwpmk/FwpmBfeStateGet0, wfp_ref_2_funct_2_fwpm_6f70e48b-0c6c-465e-95c3-fa41413398db.xml, FwpmBfeStateGet0, FwpmBfeStateGet0 function [Network Drivers Starting with Windows Vista], netvista.fwpmbfestateget0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Fwpkclnt.lib
-	Fwpkclnt.dll
apiname:
-	FwpmBfeStateGet0
product: Windows
targetos: Windows
req.typenames: PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpmBfeStateGet0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

