---
UID: NF:rxce.RxCeTearDownTransport
title: RxCeTearDownTransport function
author: windows-driver-content
description: RxCeTearDownTransport unbinds an RDBSS transport object.
old-location: ifsk\rxceteardowntransport.htm
old-project: ifsk
ms.assetid: 61376532-c78f-4a22-b8b7-ee55ddcb4b57
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxCeTearDownTransport, RxCeTearDownTransport function [Installable File System Drivers], ifsk.rxceteardowntransport, rxce/RxCeTearDownTransport, rxref_12c54611-8bbf-46bf-9ee9-35072b9322c1.xml
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
-	RxCeTearDownTransport
product: Windows
targetos: Windows
req.typenames: 
---

# RxCeTearDownTransport function


## -description


<b>RxCeTearDownTransport</b> unbinds an RDBSS transport object.


## -parameters




### -param pTransport [in]

A pointer to the RDBSS transport to be torn down.


## -returns



<b>RxCeTearDownTransport</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

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
The <i>pTransport</i> parameter passed to <b>RxCeTearDownAddress</b> or one of the data members associated with this transport was invalid. 

</td>
</tr>
</table>
 




## -remarks



When <b>RxCeTearDownTransport</b> is successful, the data members in the RXCE_TRANSPORT structure pointed to by the <i>pTransport</i> parameter will be properly uninitialized, the RDBSS transport will be released from the specified TDI transport, and allocated memory for name buffers and provider information will be freed.

If a transport that has not been bound to is specified in the <i>pTransport</i> parameter, no error is returned and the operation returns STATUS_SUCCESS. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553434">RxCeBuildTransport</a>
 

 

