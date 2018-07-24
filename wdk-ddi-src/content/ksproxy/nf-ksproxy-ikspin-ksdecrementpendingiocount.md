---
UID: NF:ksproxy.IKsPin.KsDecrementPendingIoCount
title: IKsPin::KsDecrementPendingIoCount
author: windows-driver-content
description: The KsDecrementPendingIoCount method decrements the number of input/output (I/O) operations that are in progress on a pin.
old-location: stream\ikspin_ksdecrementpendingiocount.htm
tech.root: stream
ms.assetid: 92e0355c-b89f-46c2-b406-e3c73fc37000
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IKsPin interface [Streaming Media Devices],KsDecrementPendingIoCount method, IKsPin.KsDecrementPendingIoCount, IKsPin::KsDecrementPendingIoCount, KsDecrementPendingIoCount, KsDecrementPendingIoCount method [Streaming Media Devices], KsDecrementPendingIoCount method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsDecrementPendingIoCount, ksproxy_4b423ae2-1256-4ccc-9c8d-4bd6cdb99e42.xml, stream.ikspin_ksdecrementpendingiocount
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsPin.KsDecrementPendingIoCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPin::KsDecrementPendingIoCount


## -description


The <b>KsDecrementPendingIoCount</b> method decrements the number of input/output (I/O) operations that are in progress on a pin.


## -parameters






## -returns



Returns an integer from 0 to <i>n</i>, the value that represents the new number of I/O operations that are in progress.




## -remarks



The <b>KsDecrementPendingIoCount</b> method is typically called from within an interface handler as described in the following sequence:

<ol>
<li>
The proxy creates an instance of an interface handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff559855">IKsInterfaceHandler</a>) to handle a particular media type. 

</li>
<li>
A client calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559872">IKsInterfaceHandler::KsSetPin</a> method to inform that interface handler about the pin with which to communicate when passing data. 

</li>
<li>
The client calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559869">IKsInterfaceHandler::KsProcessMediaSamples</a> method to move samples from or to the assigned pin. <b>KsProcessMediaSamples</b> performs I/O operations and for each I/O operation, calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560712">IKsPin::KsIncrementPendingIoCount</a> to increment the I/O count.

</li>
<li>
The client calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559862">IKsInterfaceHandler::KsCompleteIo</a> method to complete an I/O operation. <b>KsCompleteIo</b> calls <b>KsDecrementPendingIoCount</b> to decrement the I/O count.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559855">IKsInterfaceHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559862">IKsInterfaceHandler::KsCompleteIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559869">IKsInterfaceHandler::KsProcessMediaSamples</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559872">IKsInterfaceHandler::KsSetPin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560712">IKsPin::KsIncrementPendingIoCount</a>
 

 

