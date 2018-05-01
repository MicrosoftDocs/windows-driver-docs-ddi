---
UID: NF:fwpsk.FwpsOpenToken0
title: FwpsOpenToken0 function
author: windows-driver-content
description: The FwpsOpenToken0 function opens an access token.
old-location: netvista\fwpsopentoken0.htm
old-project: netvista
ms.assetid: B6C61023-F840-4517-83C1-BC9CBDFC27B0
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FwpsOpenToken0, FwpsOpenToken0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsOpenToken0, netvista.fwpsopentoken0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 7.
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
req.lib: 
req.dll: 
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FwpsOpenToken0
product: Windows
targetos: Windows
req.typenames: 
---

# FwpsOpenToken0 function


## -description


The <b>FwpsOpenToken0</b> function opens an access token.<div class="alert"><b>Note</b>  <b>FwpsOpenToken0</b> is a specific version of <b>FwpsOpenToken</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param engineHandle [in]

A handle for an open session to the filter engine. A callout driver calls the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550075">FwpmEngineOpen0</a> function to open a
     session to the filter engine.


### -param modifiedId [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a> that changes each time the token is modified. An application can use this value as a test of whether a security context has changed since it was last used.


### -param desiredAccess [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list (<b>DACL</b>) to determine which accesses are granted or denied.


### -param accessToken [out]

Pointer to a caller-allocated variable that receives a handle to the newly opened access token.


## -returns



The 
     <b>FwpsOpenToken0</b> function returns one of the following NTSTATUS codes.

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
The access token was successfully opened.

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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550075">FwpmEngineOpen0</a>
 

 

