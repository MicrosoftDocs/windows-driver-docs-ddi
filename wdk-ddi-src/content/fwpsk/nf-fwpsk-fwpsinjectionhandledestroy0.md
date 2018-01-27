---
UID: NF:fwpsk.FwpsInjectionHandleDestroy0
title: FwpsInjectionHandleDestroy0 function
author: windows-driver-content
description: The FwpsInjectionHandleDestroy0 function destroys an injection handle that was previously created by calling the FwpsInjectionHandleCreate0 function.Note  FwpsInjectionHandleDestroy0 is a specific version of FwpsInjectionHandleDestroy.
old-location: netvista\fwpsinjectionhandledestroy0.htm
old-project: netvista
ms.assetid: 5a00917b-36e8-4e06-a001-d8e6ac2e3573
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.fwpsinjectionhandledestroy0, FwpsInjectionHandleDestroy0, wfp_ref_2_funct_3_fwps_I_3ec9dea7-1b95-4265-b030-b88f67d21882.xml, FwpsInjectionHandleDestroy0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectionHandleDestroy0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname: 
-	FwpsInjectionHandleDestroy0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsInjectionHandleDestroy0 function


## -description


The 
  <b>FwpsInjectionHandleDestroy0</b> function destroys an injection handle that was previously created by
  calling the 
  <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a> function.
<div class="alert"><b>Note</b>  <b>FwpsInjectionHandleDestroy0</b> is a specific version of <b>FwpsInjectionHandleDestroy</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS FwpsInjectionHandleDestroy0(
  _In_ HANDLE injectionHandle
);
````


## -parameters




### -param injectionHandle [in]

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
    <mshelp:link keywords="netvista.fwpsinjectionhandlecreate0" tabindex="0"><b>
    FwpsInjectionHandleCreate0</b></mshelp:link> function. The 
    <b>FwpsInjectionHandleDestroy0</b> function will not return to the caller until all pending injections are
    completed.



## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectionHandleDestroy0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

