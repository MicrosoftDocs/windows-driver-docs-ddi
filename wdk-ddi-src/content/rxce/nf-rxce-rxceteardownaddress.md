---
UID: NF:rxce.RxCeTearDownAddress
title: RxCeTearDownAddress function (rxce.h)
description: RxCeTearDownAddress deregisters a transport address from a transport binding.
old-location: ifsk\rxceteardownaddress.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxCeTearDownAddress function"]
ms.keywords: RxCeTearDownAddress, RxCeTearDownAddress function [Installable File System Drivers], ifsk.rxceteardownaddress, rxce/RxCeTearDownAddress, rxref_99fcdd00-8c1a-4a0b-8007-5b7f01a725bb.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RxCeTearDownAddress
 - rxce/RxCeTearDownAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxce.h
api_name:
 - RxCeTearDownAddress
---

# RxCeTearDownAddress function


## -description

<b>RxCeTearDownAddress</b> deregisters a transport address from a transport binding.

## -parameters

### -param pAddress 

[in]
A pointer to the RDBSS connection engine address to deregister.

## -returns

<b>RxCeTearDownAddress</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

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
The <i>pAddress</i> parameter passed to <b>RxCeTearDownAddress</b> or one of the data members associated with this address was invalid. 

</td>
</tr>
</table>

## -remarks

When <b>RxCeTearDownAddress</b> is successful, the data members in the RXCE_ADDRESS structure pointed to by the <i>pAddress</i> parameter will be properly uninitialized, TDI addresses will be closed, and allocated memory for handlers and transport addresses will be freed.

## -see-also

<a href="/windows-hardware/drivers/ddi/rxce/nf-rxce-rxcebuildaddress">RxCeBuildAddress</a>
