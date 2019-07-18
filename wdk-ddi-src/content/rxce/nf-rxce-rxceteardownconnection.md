---
UID: NF:rxce.RxCeTearDownConnection
title: RxCeTearDownConnection function (rxce.h)
description: RxCeTearDownConnection tears down a given connection between a local RDBSS connection address and a remote address.
old-location: ifsk\rxceteardownconnection.htm
tech.root: ifsk
ms.assetid: 71b48983-af12-4361-8cf9-adec1afffb65
ms.date: 04/16/2018
ms.keywords: RxCeTearDownConnection, RxCeTearDownConnection function [Installable File System Drivers], ifsk.rxceteardownconnection, rxce/RxCeTearDownConnection, rxref_bf951adb-b63e-49f6-8325-f67adb2cdbf0.xml
ms.topic: function
f1_keywords:
 - "rxce/RxCeTearDownConnection"
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxce.h
api_name:
- RxCeTearDownConnection
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCeTearDownConnection function


## -description


<b>RxCeTearDownConnection</b> tears down a given connection between a local RDBSS connection address and a remote address.


## -parameters




### -param pConnection [in]

A pointer to an connection to be torn down.


## -returns



<b>RxCeTearDownConnection</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation of nonpaged pool memory needed by this routine failed. 

</td>
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



When <b>RxCeTearDownConnection</b> is successful, the data members in the RXCE_CONNECTION structure pointed to by the <i>pConnection</i> parameter will be properly uninitialized, and allocated memory for connection information and handler will be freed. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/rxce/nf-rxce-rxcebuildconnection">RxCeBuildConnection</a>
 

 

