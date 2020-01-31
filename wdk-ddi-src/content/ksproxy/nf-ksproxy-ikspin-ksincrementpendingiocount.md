---
UID: NF:ksproxy.IKsPin.KsIncrementPendingIoCount
title: IKsPin::KsIncrementPendingIoCount (ksproxy.h)
description: The KsIncrementPendingIoCount method increments the number of input/output (I/O) operations that are in progress on a pin.
old-location: stream\ikspin_ksincrementpendingiocount.htm
tech.root: stream
ms.assetid: e79ae2ac-6636-491d-8c98-70a5ff3a23ef
ms.date: 04/23/2018
ms.keywords: IKsPin interface [Streaming Media Devices],KsIncrementPendingIoCount method, IKsPin.KsIncrementPendingIoCount, IKsPin::KsIncrementPendingIoCount, KsIncrementPendingIoCount, KsIncrementPendingIoCount method [Streaming Media Devices], KsIncrementPendingIoCount method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsIncrementPendingIoCount, ksproxy_c654f701-d58e-4953-ad55-76d98096b7f0.xml, stream.ikspin_ksincrementpendingiocount
f1_keywords:
 - "ksproxy/IKsPin.KsIncrementPendingIoCount"
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
- IKsPin.KsIncrementPendingIoCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPin::KsIncrementPendingIoCount


## -description


The <b>KsIncrementPendingIoCount</b> method increments the number of input/output (I/O) operations that are in progress on a pin.


## -returns



Returns an integer from 1 to <i>n</i>, the value that represents the new number of I/O operations that are in progress.




## -remarks



The <b>KsIncrementPendingIoCount</b> method is typically called from within an interface handler as described in the following sequence:

<ol>
<li>
The proxy creates an instance of an interface handler (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>) to handle a particular media type. 

</li>
<li>
A client calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-kssetpin">IKsInterfaceHandler::KsSetPin</a> method to inform that interface handler about the pin with which to communicate when passing data. 

</li>
<li>
The client calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-ksprocessmediasamples">IKsInterfaceHandler::KsProcessMediaSamples</a> method to move samples from or to the assigned pin. <b>KsProcessMediaSamples</b> performs I/O operations and for each I/O operation, calls <b>KsIncrementPendingIoCount</b> to increment the I/O count.

</li>
<li>
The client calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-kscompleteio">IKsInterfaceHandler::KsCompleteIo</a> method to complete an I/O operation. <b>KsCompleteIo</b> calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspin-ksdecrementpendingiocount">IKsPin::KsDecrementPendingIoCount</a> to decrement the I/O count.

</li>
</ol>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-kscompleteio">IKsInterfaceHandler::KsCompleteIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-ksprocessmediasamples">IKsInterfaceHandler::KsProcessMediaSamples</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-kssetpin">IKsInterfaceHandler::KsSetPin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspin-ksdecrementpendingiocount">IKsPin::KsDecrementPendingIoCount</a>
 

 

