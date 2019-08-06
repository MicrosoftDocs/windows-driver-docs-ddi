---
UID: NF:rxce.RxCeSendDatagram
title: RxCeSendDatagram function (rxce.h)
description: RxCeSendDatagram sends a transport service data unit (TSDU) along the specified connection on a virtual circuit.
old-location: ifsk\rxcesenddatagram.htm
tech.root: ifsk
ms.assetid: 9cb714d5-92f6-481d-bc5e-5fa05b6a0938
ms.date: 04/16/2018
ms.keywords: RxCeSendDatagram, RxCeSendDatagram function [Installable File System Drivers], ifsk.rxcesenddatagram, rxce/RxCeSendDatagram, rxref_dc97dbe7-c676-4b1f-8aee-7dbc7cfbc5e3.xml
ms.topic: function
f1_keywords:
 - "rxce/RxCeSendDatagram"
req.header: rxce.h
req.include-header: Rxce.h, Tdi.h
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
- RxCeSendDatagram
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCeSendDatagram function


## -description


<b>RxCeSendDatagram</b> sends a transport service data unit (TSDU) along the specified connection on a virtual circuit.


## -parameters




### -param hAddress

<p>A pointer to the transport along which the TSDU is to be sent.</p>


### -param pConnectionInformation [in]

A pointer to connection information that contains the remote address.


### -param SendOptions

<p>A pointer to connection information that contains the remote address.</p>


### -param pMdl [in]

A pointer to the buffer to be sent.


### -param SendLength [in]

The length of data to be sent.


### -param pCompletionContext [in]

The context passed back to the caller during <b>SendCompletion</b> for asynchronous operations. Not that this parameter is ignored if the <i>Options</i> parameter requests a synchronous send operation.


## -returns



<b>RxCeSendDatagram</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

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
An invalid length was passed in the <i>SendLength</i> parameter based on the <i>Options</i> specified.

</td>
</tr>
</table>
 




## -remarks



The asynchronous and synchronous options indicated in the <i>Options</i> parameter used in <b>RxCeSendDatagram</b> distinguish between two situations. In the asynchronous case, control returns to the caller once the request has been successfully submitted to the underlying transport. The results for any given request are communicated back using the <b>SendCompletion</b> callback routine. The <i>pCompletionContext</i> parameter in <b>RxCeSendDatagram</b> is passed back in the callback routine to assist the caller in disambiguating the requests.

In the synchronous case, the request is submitted to the underlying transport and the control does not return to the caller till the request completes. Note that in the synchronous case, the <i>pCompletionContext</i> parameter is ignored and the status that is returned corresponds to the completion status of the operations.

The benefit of asynchronous and synchronous options depends on the underlying transport. In a virtual circuit environment (TCP, for example), a synchronous option implies that the control does not return until the data reaches the server. On the other hand for datagram oriented transports (UDP, for example), there is very little difference between the two options.

Note that the synchronous <i>Option</i> is disregarded for sending datagrams because the underlying transports do not block on datagram sends. 

<b>RXCE_CONNECTION_INFORMATION</b> is a typedef for a <b>TDI_CONNECTION_INFORMATION</b> structure. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/rxce/nf-rxce-rxcesend">RxCeSend</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565085(v=vs.85)">TDI_CONNECTION_INFORMATION</a>
 

 

