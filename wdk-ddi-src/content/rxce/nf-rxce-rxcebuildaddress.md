---
UID: NF:rxce.RxCeBuildAddress
title: RxCeBuildAddress function
author: windows-driver-content
description: RxCeBuildAddress associates a transport address with a transport binding.
old-location: ifsk\rxcebuildaddress.htm
old-project: ifsk
ms.assetid: e8845b15-4427-45ea-9192-352d82c89c6a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxCeBuildAddress, RxCeBuildAddress function [Installable File System Drivers], ifsk.rxcebuildaddress, rxce/RxCeBuildAddress, rxref_ee32329f-3111-4ee6-869f-2b8e21d6696c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxce.h
api_name:
-	RxCeBuildAddress
product: Windows
targetos: Windows
req.typenames: 
---

# RxCeBuildAddress function


## -description


<b>RxCeBuildAddress</b> associates a transport address with a transport binding.


## -parameters




### -param pAddress [in, out]

On input, this parameter contains a pointer to an uninitialized RDBSS connection engine address structure. On output when this call is successful, the data members in the RXCE_ADDRESS structure will be properly initialized.


### -param pTransport [in]

A pointer to the transport with which this address is to be associated.


### -param pTransportAddress [in]

A pointer to the transport address to be associated with the binding.


### -param pHandler [in]

A pointer to the event handler associated with the registration.


### -param pEventContext [in]

A pointer to the context parameter to be passed back to the event handler.


## -returns



<b>RxCeBuildAddress</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

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
One of the parameters passed to <b>RxCeBuildAddress</b> was invalid. 

</td>
</tr>
</table>
 




## -remarks



When <b>RxCeBuildAddress</b> is successful, the data members in the RXCE_ADDRESS structure pointed to by the <i>pAddress</i> parameter will be properly initialized. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553488">RxCeTearDownAddress</a>
 

 

