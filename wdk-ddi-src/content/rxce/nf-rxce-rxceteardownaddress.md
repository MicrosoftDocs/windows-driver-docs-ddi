---
UID: NF:rxce.RxCeTearDownAddress
title: RxCeTearDownAddress function
author: windows-driver-content
description: RxCeTearDownAddress deregisters a transport address from a transport binding.
old-location: ifsk\rxceteardownaddress.htm
old-project: ifsk
ms.assetid: 76fd7c35-fef1-43c2-aedd-d09d18ab27a4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCeTearDownAddress, RxCeTearDownAddress function [Installable File System Drivers], ifsk.rxceteardownaddress, rxce/RxCeTearDownAddress, rxref_99fcdd00-8c1a-4a0b-8007-5b7f01a725bb.xml
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
-	RxCeTearDownAddress
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeTearDownAddress function


## -description


<b>RxCeTearDownAddress</b> deregisters a transport address from a transport binding.


## -parameters




### -param pAddress [in]

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553414">RxCeBuildAddress</a>
 

 

