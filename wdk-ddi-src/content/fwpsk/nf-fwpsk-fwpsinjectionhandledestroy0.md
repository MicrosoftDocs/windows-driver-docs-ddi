---
UID: NF:fwpsk.FwpsInjectionHandleDestroy0
title: FwpsInjectionHandleDestroy0 function (fwpsk.h)
description: The FwpsInjectionHandleDestroy0 function destroys an injection handle that was previously created by calling the FwpsInjectionHandleCreate0 function.Note  FwpsInjectionHandleDestroy0 is a specific version of FwpsInjectionHandleDestroy.
old-location: netvista\fwpsinjectionhandledestroy0.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FwpsInjectionHandleDestroy0 function"]
ms.keywords: FwpsInjectionHandleDestroy0, FwpsInjectionHandleDestroy0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectionHandleDestroy0, netvista.fwpsinjectionhandledestroy0, wfp_ref_2_funct_3_fwps_I_3ec9dea7-1b95-4265-b030-b88f67d21882.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsInjectionHandleDestroy0
 - fwpsk/FwpsInjectionHandleDestroy0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsInjectionHandleDestroy0
---

# FwpsInjectionHandleDestroy0 function


## -description

The 
  <b>FwpsInjectionHandleDestroy0</b> function destroys an injection handle that was previously created by
  calling the 
  <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a> function.
<div class="alert"><b>Note</b>  <b>FwpsInjectionHandleDestroy0</b> is a specific version of <b>FwpsInjectionHandleDestroy</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param injectionHandle 

[in]
The injection handle being destroyed.

## -returns

The 
     <b>FwpsInjectionHandleDestroy0</b> function returns one of the following NTSTATUS codes.

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
The injection handle was successfully destroyed.

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
    <b>FwpsInjectionHandleDestroy0</b> function to destroy an injection handle that was previously created by
    calling the 
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">
    FwpsInjectionHandleCreate0</a> function. The 
    <b>FwpsInjectionHandleDestroy0</b> function will not return to the caller until all pending injections are
    completed.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a>
