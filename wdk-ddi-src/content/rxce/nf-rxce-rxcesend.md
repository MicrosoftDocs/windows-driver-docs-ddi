---
UID: NF:rxce.RxCeSend
title: RxCeSend function
author: windows-driver-content
description: RxCeSend sends a transport service data unit (TSDU) along the specified connection on a virtual circuit.
old-location: ifsk\rxcesend.htm
old-project: ifsk
ms.assetid: bf1b9c63-6fc2-4006-8f9a-d4b50d61d270
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rxce/RxCeSend, rxref_07c5b21c-253c-4032-a5e8-61c4e71450fb.xml, RxCeSend function [Installable File System Drivers], RxCeSend, ifsk.rxcesend
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxce.h
apiname:
-	RxCeSend
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeSend function


## -description


<b>RxCeSend</b> sends a transport service data unit (TSDU) along the specified connection on a virtual circuit.


## -syntax


````
NTSTATUS RxCeSend(
  _In_ PRXCE_VC pVc,
  _In_ ULONG    SendOptions,
  _In_ PMDL     pMdl,
  _In_ ULONG    SendLength,
  _In_ PVOID    pCompletionContext
);
````


## -parameters




### -param pVc [in]

A pointer to the virtual circuit along which the TSDU is to be sent.


### -param SendOptions [in]

The desired options for transmitting the data on this send operation by the transport. Note that this is only a request sent to the transport. The transport may only support a limited number of the options specified and ignore options not supported. The <i>SendOptions</i> parameter consists of a set of bits defined in <i>rxce.h</i>. The <i>SendOptions</i> parameter can be a combination of the following bits:





#### RXCE_SEND_EXPEDITED

The given data should be sent ahead of any normal send requests the transport is currently holding queued for transmission on this endpoint-to-endpoint connection. If the transport does not support expedited transfers, it can ignore this flag. Note that RXCE_SEND_EXPEDITED is equivalent to the TDI TDI_SEND_EXPEDITED flag.



#### RXCE_SEND_NO_RESPONSE_EXPECTED

The caller is giving a hint to the underlying transport that it does not expect a response to this send from its remote-node peer. This flag should disable piggybacking of the TSDU acknowledgment by the remote-node transport. Note that RXCE_SEND_NO_RESPONSE_EXPECTED is equivalent to the TDI_SEND_NO_RESPONSE_EXPECTED flag.



#### RXCE_SEND_NON_BLOCKING

If the underlying transport currently has no internal buffer space available for the given data, it should just complete the IRP with STATUS_DEVICE_NOT_READY. If the transport has some buffer space available, it should copy as much data as it can from the client-supplied buffer, set the <b>IoStatus.Information</b> member to the number of bytes it copied, and complete the IRP with STATUS_SUCCESS. 

This flag is irrelevant to transports that do not buffer sends internally. Note that RXCE_SEND_NON_BLOCKING is equivalent to the TDI_SEND_NON_BLOCKING flag.



#### RXCE_SEND_PARTIAL

Signifies if an RX_MEM_DESC(MDL) is to be sent in its entirety, or if only portions of it need to be sent. This option requests that the transport allow the send operation to transmit part of the data if the transport and MDL allow this behavior.



#### RXCE_SEND_SYNCHRONOUS

Signifies if the send operation is to transmit the data synchronously. When this option is set, the request is submitted to the underlying transport and control does not return to the caller until the request completes. Note that the <i>pCompletionContext</i> parameter is ignored when this bit is set.


### -param pMdl [in]

A pointer to the buffer to be sent.


### -param SendLength [in]

The length of data to be sent.


### -param pCompletionContext [in]

The context passed back to the caller during <b>SendCompletion</b> for asynchronous operations. Not that this parameter is ignored if the <i>SendOptions</i> parameter requests a synchronous send operation.


## -returns



<b>RxCeSend</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_DISCONNECTED</b></dt>
</dl>
</td>
<td width="60%">
An invalid or disconnected virtual circuit or connection was specified

</td>
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
An invalid length was passed in the <i>SendLength</i> parameter based on the <i>SendOptions</i> specified.

</td>
</tr>
</table>
 




## -remarks



The <b>RxCeSend</b> routine will allocate the IRP, build the send request for the underlying transport driver, and submit the request to TDI. In the case of synchronous send operations, this routine will also the free IRP and resources allocated when the routine completes.

The asynchronous and synchronous options indicated in the <i>SendOptions</i> parameter used in <b>RxCeSend</b> distinguish between two situations. In the asynchronous case, control returns to the caller once the request has been successfully submitted to the underlying transport. The results for any given request are communicated back using the <b>SendCompletion</b> callback routine. The <i>pCompletionContext</i> parameter in <b>RxCeSend</b> is passed back in the callback routine to assist the caller in disambiguating the requests.

In the synchronous case, the request is submitted to the underlying transport and the control does not return to the caller till the request completes. Note that in the synchronous case, the <i>pCompletionContext</i> parameter is ignored and the status that is returned corresponds to the completion status of the operations.

The benefit of asynchronous and synchronous options depends on the underlying transport. In a virtual circuit environment (TCP, for example), a synchronous option implies that the control does not return until the data reaches the server. On the other hand for datagram oriented transports (UDP, for example), there is very little difference between the two options.




## -see-also

<a href="..\rxce\nf-rxce-rxcesenddatagram.md">RxCeSendDatagram</a>



<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeSend function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

