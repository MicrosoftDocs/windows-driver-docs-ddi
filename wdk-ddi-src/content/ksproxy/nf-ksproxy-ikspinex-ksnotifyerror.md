---
UID: NF:ksproxy.IKsPinEx.KsNotifyError
title: IKsPinEx::KsNotifyError (ksproxy.h)
description: The KsNotifyError method notifies the filter graph of an error to give the filter graph an opportunity to halt.
old-location: stream\ikspinex_ksnotifyerror.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsPinEx::KsNotifyError"]
ms.keywords: IKsPinEx interface [Streaming Media Devices],KsNotifyError method, IKsPinEx.KsNotifyError, IKsPinEx::KsNotifyError, KsNotifyError, KsNotifyError method [Streaming Media Devices], KsNotifyError method [Streaming Media Devices],IKsPinEx interface, ksproxy/IKsPinEx::KsNotifyError, ksproxy_41c855aa-58a3-4bf6-bb8a-1eb8dfe2a3e1.xml, stream.ikspinex_ksnotifyerror
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsPinEx::KsNotifyError
 - ksproxy/IKsPinEx::KsNotifyError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPinEx.KsNotifyError
---

# IKsPinEx::KsNotifyError


## -description

The <b>KsNotifyError</b> method notifies the filter graph of an error to give the filter graph an opportunity to halt.

## -parameters

### -param Sample 

[in]
Pointer to the <b>IMediaSample</b> interface for the associated media sample.

### -param hr 

[in]
Error value for notification. If ERROR_OPERATION_ABORTED (that is, the I/O was purposefully canceled), the filter graph is not notified.

## -remarks

The <b>KsNotifyError</b> method notifies the filter graph of the specific error using the EC_ERRORABORT event, which specifies that the error forced the termination of an I/O operation.

For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikspinex">IKsPinEx</a>
