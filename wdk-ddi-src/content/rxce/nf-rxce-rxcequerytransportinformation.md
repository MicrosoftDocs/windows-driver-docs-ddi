---
UID: NF:rxce.RxCeQueryTransportInformation
title: RxCeQueryTransportInformation function (rxce.h)
description: RxCeQueryTransportInformation queries transport information for a given transport.
old-location: ifsk\rxcequerytransportinformation.htm
tech.root: ifsk
ms.assetid: 94744af6-0c62-4942-a8a8-3a45a0ab98da
ms.date: 04/16/2018
keywords: ["RxCeQueryTransportInformation function"]
ms.keywords: RxCeQueryTransportInformation, RxCeQueryTransportInformation function [Installable File System Drivers], ifsk.rxcequerytransportinformation, rxce/RxCeQueryTransportInformation, rxref_db01b7e1-b0ea-4d42-99b8-c9b55fc34fb6.xml
f1_keywords:
 - "rxce/RxCeQueryTransportInformation"
 - "RxCeQueryTransportInformation"
req.header: rxce.h
req.include-header: Rxce.h, Rxcehdlr.h, Tdi.h
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
- RxCeQueryTransportInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCeQueryTransportInformation function


## -description


<b>RxCeQueryTransportInformation</b> queries transport information for a given transport.


## -parameters




### -param pTransport

A pointer to the transport.


### -param pTransportInformation

A pointer to the caller-supplied buffer for returning information. 


## -returns



<b>RxCeQueryTransportInformation</b> returns STATUS_SUCCESS on success or the following error code on failure: 

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
This value can be returned for any of the following conditions:

<dl>
<dd>
The <i>pTransport</i> parameter passed to this routine was invalid.

</dd>
<dd>
The <i>pTransportInformation</i> parameter did not point to allocated memory large enough to hold an <b>RXCE_TRANSPORT_INFORMATION</b> data structure. 

</dd>
</dl>
</td>
</tr>
</table>
 




## -remarks



<b>RxCeQueryTransportInformation</b> returns information for a given transport. The <b>RXCE_TRANSPORT_INFORMATION</b> data structure contains two data elements that are filled in by <b>RxCeQueryTransportInformation</b>:

ConnectionCount

QualityOfService




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxce/nf-rxce-rxcequeryadapterstatus">RxCeQueryAdapterStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxce/nf-rxce-rxcequeryinformation">RxCeQueryInformation</a>
 

 

