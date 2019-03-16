---
UID: NF:ksproxy.IKsPinEx.KsNotifyError
title: IKsPinEx::KsNotifyError (ksproxy.h)
description: The KsNotifyError method notifies the filter graph of an error to give the filter graph an opportunity to halt.
old-location: stream\ikspinex_ksnotifyerror.htm
tech.root: stream
ms.assetid: a2526734-c0bf-4f6b-b91e-2f6891c46c69
ms.date: 04/23/2018
ms.keywords: IKsPinEx interface [Streaming Media Devices],KsNotifyError method, IKsPinEx.KsNotifyError, IKsPinEx::KsNotifyError, KsNotifyError, KsNotifyError method [Streaming Media Devices], KsNotifyError method [Streaming Media Devices],IKsPinEx interface, ksproxy/IKsPinEx::KsNotifyError, ksproxy_41c855aa-58a3-4bf6-bb8a-1eb8dfe2a3e1.xml, stream.ikspinex_ksnotifyerror
ms.topic: method
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsPinEx.KsNotifyError
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPinEx::KsNotifyError


## -description


The <b>KsNotifyError</b> method notifies the filter graph of an error to give the filter graph an opportunity to halt. 


## -parameters




### -param Sample [in]

Pointer to the <b>IMediaSample</b> interface for the associated media sample.


### -param hr [in]

Error value for notification. If ERROR_OPERATION_ABORTED (that is, the I/O was purposefully canceled), the filter graph is not notified. 


## -returns



None




## -remarks



The <b>KsNotifyError</b> method notifies the filter graph of the specific error using the EC_ERRORABORT event, which specifies that the error forced the termination of an I/O operation.

For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559902">IKsPinEx</a>
 

 

