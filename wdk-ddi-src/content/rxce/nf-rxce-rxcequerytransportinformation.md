---
UID: NF:rxce.RxCeQueryTransportInformation
title: RxCeQueryTransportInformation function
author: windows-driver-content
description: RxCeQueryTransportInformation queries transport information for a given transport.
old-location: ifsk\rxcequerytransportinformation.htm
old-project: ifsk
ms.assetid: 94744af6-0c62-4942-a8a8-3a45a0ab98da
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxCeQueryTransportInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h, Rxcehdlr.h, Tdi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxCeQueryTransportInformation
req.alt-loc: rxce.h
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
req.typenames: *LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeQueryTransportInformation function



## -description
<b>RxCeQueryTransportInformation</b> queries transport information for a given transport.



## -syntax

````
NTSTATUS RxCeQueryTransportInformation(
   PRXCE_TRANSPORT             pTransport,
   PRXCE_TRANSPORT_INFORMATION pTransportInformation
);
````


## -parameters

### -param pTransport 

A pointer to the transport.


### -param pTransportInformation 

A pointer to the caller-supplied buffer for returning information. 


## -returns
<b>RxCeQueryTransportInformation</b> returns STATUS_SUCCESS on success or the following error code on failure: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This value can be returned for any of the following conditions:
<dl>
<dd>
The <i>pTransport</i> parameter passed to this routine was invalid.

</dd>
<dd>
The <i>pTransportInformation</i> parameter did not point to allocated memory large enough to hold an <b>RXCE_TRANSPORT_INFORMATION</b> data structure. 

</dd>
</dl>The <i>pTransport</i> parameter passed to this routine was invalid.

The <i>pTransportInformation</i> parameter did not point to allocated memory large enough to hold an <b>RXCE_TRANSPORT_INFORMATION</b> data structure. 

 


## -remarks
<b>RxCeQueryTransportInformation</b> returns information for a given transport. The <b>RXCE_TRANSPORT_INFORMATION</b> data structure contains two data elements that are filled in by <b>RxCeQueryTransportInformation</b>:

ConnectionCount

QualityOfService


## -see-also
<dl>
<dt>
<a href="..\rxce\nf-rxce-rxcequeryadapterstatus.md">RxCeQueryAdapterStatus</a>
</dt>
<dt>
<a href="..\rxce\nf-rxce-rxcequeryinformation.md">RxCeQueryInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeQueryTransportInformation function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

