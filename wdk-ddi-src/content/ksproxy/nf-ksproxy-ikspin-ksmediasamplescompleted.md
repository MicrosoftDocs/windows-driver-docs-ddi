---
UID: NF:ksproxy.IKsPin.KsMediaSamplesCompleted
title: IKsPin::KsMediaSamplesCompleted method
author: windows-driver-content
description: The KsMediaSamplesCompleted method informs a pin that a stream segment completed.
old-location: stream\ikspin_ksmediasamplescompleted.htm
old-project: stream
ms.assetid: df3bbc09-14aa-4243-887b-d88d02a59f73
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsPin, IKsPin::KsMediaSamplesCompleted, KsMediaSamplesCompleted
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
req.alt-api: IKsPin.KsMediaSamplesCompleted
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

# IKsPin::KsMediaSamplesCompleted method



## -description
The <b>KsMediaSamplesCompleted</b> method informs a pin that a stream segment completed. 



## -syntax

````
HRESULT KsMediaSamplesCompleted(
  [in] PKSSTREAM_SEGMENT StreamSegment
);
````


## -parameters

### -param StreamSegment [in]

Pointer to a <a href="..\ksproxy\ns-ksproxy-_ksstream_segment.md">KSSTREAM_SEGMENT</a> structure that contains header information for a completed stream segment. 


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks
Input pins do nothing with the supplied header information and just return NOERROR. Output pins remove the head of the input and output (I/O) queue and add the next in the list to the I/O slots.

When a client calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559862">IKsInterfaceHandler::KsCompleteIo</a> method of an interface handler to complete an I/O operation, <b>KsCompleteIo</b> calls <b>KsMediaSamplesCompleted</b> for pins. 


## -see-also
<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559862">IKsInterfaceHandler::KsCompleteIo</a>
</dt>
<dt>
<a href="..\ksproxy\ns-ksproxy-_ksstream_segment.md">KSSTREAM_SEGMENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPin::KsMediaSamplesCompleted method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

