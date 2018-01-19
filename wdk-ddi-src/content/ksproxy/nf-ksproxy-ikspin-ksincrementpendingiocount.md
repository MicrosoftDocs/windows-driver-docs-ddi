---
UID: NF:ksproxy.IKsPin.KsIncrementPendingIoCount
title: IKsPin::KsIncrementPendingIoCount method
author: windows-driver-content
description: The KsIncrementPendingIoCount method increments the number of input/output (I/O) operations that are in progress on a pin.
old-location: stream\ikspin_ksincrementpendingiocount.htm
old-project: stream
ms.assetid: e79ae2ac-6636-491d-8c98-70a5ff3a23ef
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsPin, IKsPin::KsIncrementPendingIoCount, KsIncrementPendingIoCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsPin.KsIncrementPendingIoCount
req.alt-loc: ksproxy.h
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
req.typenames: PIPE_STATE
---

# IKsPin::KsIncrementPendingIoCount method



## -description
The <b>KsIncrementPendingIoCount</b> method increments the number of input/output (I/O) operations that are in progress on a pin.



## -syntax

````
LONG KsIncrementPendingIoCount();
````


## -parameters


## -returns
Returns an integer from 1 to <i>n</i>, the value that represents the new number of I/O operations that are in progress.

Returns an integer from 1 to <i>n</i>, the value that represents the new number of I/O operations that are in progress.

Returns an integer from 1 to <i>n</i>, the value that represents the new number of I/O operations that are in progress.


## -remarks
The <b>KsIncrementPendingIoCount</b> method is typically called from within an interface handler as described in the following sequence:

The proxy creates an instance of an interface handler (<a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a>) to handle a particular media type. 

A client calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559872">IKsInterfaceHandler::KsSetPin</a> method to inform that interface handler about the pin with which to communicate when passing data. 

The client calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559869">IKsInterfaceHandler::KsProcessMediaSamples</a> method to move samples from or to the assigned pin. <b>KsProcessMediaSamples</b> performs I/O operations and for each I/O operation, calls <b>KsIncrementPendingIoCount</b> to increment the I/O count.

The client calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559862">IKsInterfaceHandler::KsCompleteIo</a> method to complete an I/O operation. <b>KsCompleteIo</b> calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560709">IKsPin::KsDecrementPendingIoCount</a> to decrement the I/O count.


## -see-also
<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559862">IKsInterfaceHandler::KsCompleteIo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559869">IKsInterfaceHandler::KsProcessMediaSamples</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559872">IKsInterfaceHandler::KsSetPin</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560709">IKsPin::KsDecrementPendingIoCount</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPin::KsIncrementPendingIoCount method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

