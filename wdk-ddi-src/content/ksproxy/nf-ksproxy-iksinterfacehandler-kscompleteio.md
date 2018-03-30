---
UID: NF:ksproxy.IKsInterfaceHandler.KsCompleteIo
title: IKsInterfaceHandler::KsCompleteIo method
author: windows-driver-content
description: The KsCompleteIo method cleans up extended headers and releases media samples after input and output (I/O) complete.
old-location: stream\iksinterfacehandler_kscompleteio.htm
old-project: stream
ms.assetid: 2ff69f59-5fbd-43fd-afe5-9717d7928d2a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsInterfaceHandler, IKsInterfaceHandler interface [Streaming Media Devices], KsCompleteIo method, IKsInterfaceHandler::KsCompleteIo, KsCompleteIo method [Streaming Media Devices], KsCompleteIo method [Streaming Media Devices], IKsInterfaceHandler interface, KsCompleteIo,IKsInterfaceHandler.KsCompleteIo, ksproxy/IKsInterfaceHandler::KsCompleteIo, ksproxy_3f49ef68-7608-4348-ba18-ffd3bb0e7808.xml, stream.iksinterfacehandler_kscompleteio
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
-	IKsInterfaceHandler.KsCompleteIo
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsInterfaceHandler::KsCompleteIo method


## -description


The <b>KsCompleteIo</b> method cleans up extended headers and releases media samples after input and output (I/O) complete. 


## -parameters




### -param StreamSegment [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567141">KSSTREAM_SEGMENT</a> structure that contains header information for a stream segment to complete. 


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The <b>KsCompleteIo</b> method discards allocated memory, updates media samples, and decrements the count of wait items for the proxy. 

The <b>KsCompleteIo</b> method must determine the type of I/O operation that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559869">IKsInterfaceHandler::KsProcessMediaSamples</a> method completed from the <b>IoOperation</b> member of the KSSTREAM_SEGMENT structure. If the I/O operation was reading data from a stream (<b>KsIoOperation_Read</b> of the KSIOOPERATION enumerated type), <b>KsCompleteIo</b> performs the following actions to deliver the sample from an output pin to the connected input pin:

<ul>
<li>
Reflects the stream header information in the <b>IMediaSample</b> interface. 

</li>
<li>
Calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560710">IKsPin::KsDeliver</a> method of the output pin to deliver the sample. <b>KsDeliver</b> releases the sample so that when queuing buffers to the device, the sample can be retrieved if it is the last sample. The input pin then completes the I/O and it is safe to release the sample. 

</li>
</ul>
For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559869">IKsInterfaceHandler::KsProcessMediaSamples</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560710">IKsPin::KsDeliver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567141">KSSTREAM_SEGMENT</a>
 

 

