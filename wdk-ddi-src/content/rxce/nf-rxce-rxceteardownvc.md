---
UID: NF:rxce.RxCeTearDownVC
title: RxCeTearDownVC function (rxce.h)
description: RxCeTearDownVC deregisters a virtual circuit from a specified RDBSS connection.
old-location: ifsk\rxceteardownvc.htm
tech.root: ifsk
ms.assetid: d4b3af4d-8bb2-42a4-a8d9-baa643a90418
ms.date: 04/16/2018
keywords: ["RxCeTearDownVC function"]
ms.keywords: RxCeTearDownVC, RxCeTearDownVC function [Installable File System Drivers], ifsk.rxceteardownvc, rxce/RxCeTearDownVC, rxref_12c4b02d-b629-4543-bf74-aeaa14f6f05d.xml
f1_keywords:
 - "rxce/RxCeTearDownVC"
 - "RxCeTearDownVC"
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxce.h
api_name:
- RxCeTearDownVC
targetos: Windows
req.typenames: 
---

# RxCeTearDownVC function


## -description


<b>RxCeTearDownVC</b> deregisters a virtual circuit from a specified RDBSS connection.


## -parameters




### -param pVc 
[in]
A pointer to a handle for an virtual circuit structure to be torn down. 


## -returns



<b>RxCeTearDownVC</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters passed to this routine was invalid. 

</td>
</tr>
</table>
 




## -remarks



When <b>RxCeTearDownVC</b> is successful, the data members in the RXCE_VC structure pointed to by the <i>pVC</i> parameter will be properly uninitialized and the virtual circuit will be disconnected from the associated RDBSS transport, address, and connection. 

Note that <b>RxCeTearDownVC</b> will wait for the clean up of connections over other transports to be completed before returning.

<b>RxCeTearDownVC</b> calls TDI to disconnect the virtual circuit associated with a connection. If the call to TDI is unsuccessful, <b>RxCeTearDownVC</b> will return the error from the TDI routine call. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxce/nf-rxce-rxcebuildvc">RxCeBuildVC</a>
 

 

