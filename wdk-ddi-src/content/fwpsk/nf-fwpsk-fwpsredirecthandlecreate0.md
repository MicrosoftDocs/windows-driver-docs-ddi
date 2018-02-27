---
UID: NF:fwpsk.FwpsRedirectHandleCreate0
title: FwpsRedirectHandleCreate0 function
author: windows-driver-content
description: The FwpsRedirectHandleCreate0 function creates a handle that connection redirection functions can use to redirect connections to a local process.
old-location: netvista\fwpsredirecthandlecreate0.htm
old-project: netvista
ms.assetid: 841f3885-509a-457e-854d-e8ead657de54
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FwpsRedirectHandleCreate0, FwpsRedirectHandleCreate0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsRedirectHandleCreate0, netvista.fwpsredirecthandlecreate0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	FwpsRedirectHandleCreate0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsRedirectHandleCreate0 function


## -description


The <b>FwpsRedirectHandleCreate0</b> function creates a handle that  connection redirection functions can use to redirect connections to a local process. For more information about redirection, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect Redirection</a>.<div class="alert"><b>Note</b>  <b>FwpsRedirectHandleCreate0</b> is a specific version of <b>FwpsRedirectHandleCreate</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -syntax


````
NTSTATUS NTAPI FwpsRedirectHandleCreate0(
   _In_ const GUID        *providerGuid,
   _In_ _Reserved_ UINT32 flags,
   _Out_ HANDLE           *redirectHandle
);
````


## -parameters




### -param providerGuid

The provider GUID.


### -param flags

Reserved.  Set to zero.


### -param redirectHandle

A pointer to the variable that receives the handle.


## -returns



The 
     <b>FwpsRedirectHandleCreate0</b> function returns one of the following NTSTATUS codes.

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
A redirect handle was successfully returned. The variable that the 
       <i>redirectHandle</i> parameter points to contains the handle.

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



A callout driver calls the <b>FwpsRedirectHandleCreate0</b> function to create a handle that can be used to redirect connections.

For more information about redirection, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-bind-or-connect-redirection">Using Bind or Connect Redirection</a>.

Your callout driver should call <b>FwpsRedirectHandleCreate0</b> once and cache the handle so that it can reuse the handle.

Before an Application Layer Enforcement (ALE) connect redirection callout can redirect connections to a local process, it must  obtain a redirect handle with the <b>FwpsRedirectHandleCreate0</b> function and put the handle in the <a href="..\fwpsk\ns-fwpsk-_fwps_connect_request0.md">FWPS_CONNECT_REQUEST0</a> structure. The callout modifies the structure in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> for the ALE connect redirect layers.

After a callout driver has finished using a redirect handle, it must call the <a href="..\fwpsk\nf-fwpsk-fwpsredirecthandledestroy0.md">FwpsRedirectHandleDestroy0</a> function to destroy the handle. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>



<a href="..\fwpsk\ns-fwpsk-_fwps_connect_request0.md">FWPS_CONNECT_REQUEST0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsredirecthandledestroy0.md">FwpsRedirectHandleDestroy0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsRedirectHandleCreate0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

