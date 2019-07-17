---
UID: NF:ksproxy.IKsPin.KsMediaSamplesCompleted
title: IKsPin::KsMediaSamplesCompleted (ksproxy.h)
description: The KsMediaSamplesCompleted method informs a pin that a stream segment completed.
old-location: stream\ikspin_ksmediasamplescompleted.htm
tech.root: stream
ms.assetid: df3bbc09-14aa-4243-887b-d88d02a59f73
ms.date: 04/23/2018
ms.keywords: IKsPin interface [Streaming Media Devices],KsMediaSamplesCompleted method, IKsPin.KsMediaSamplesCompleted, IKsPin::KsMediaSamplesCompleted, KsMediaSamplesCompleted, KsMediaSamplesCompleted method [Streaming Media Devices], KsMediaSamplesCompleted method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsMediaSamplesCompleted, ksproxy_06b7c470-0755-4cae-a346-15f544c51d1d.xml, stream.ikspin_ksmediasamplescompleted
ms.topic: method
f1_keywords:
 - "ksproxy/IKsPin.KsMediaSamplesCompleted"
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
- IKsPin.KsMediaSamplesCompleted
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPin::KsMediaSamplesCompleted


## -description


The <b>KsMediaSamplesCompleted</b> method informs a pin that a stream segment completed. 


## -parameters




### -param StreamSegment [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/ns-ksproxy-_ksstream_segment">KSSTREAM_SEGMENT</a> structure that contains header information for a completed stream segment. 


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



Input pins do nothing with the supplied header information and just return NOERROR. Output pins remove the head of the input and output (I/O) queue and add the next in the list to the I/O slots.

When a client calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-iksinterfacehandler-kscompleteio">IKsInterfaceHandler::KsCompleteIo</a> method of an interface handler to complete an I/O operation, <b>KsCompleteIo</b> calls <b>KsMediaSamplesCompleted</b> for pins. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-iksinterfacehandler-kscompleteio">IKsInterfaceHandler::KsCompleteIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/ns-ksproxy-_ksstream_segment">KSSTREAM_SEGMENT</a>
 

 

