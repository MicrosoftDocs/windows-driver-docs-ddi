---
UID: NF:ksproxy.IKsPin.KsQueryMediums
title: IKsPin::KsQueryMediums method
author: windows-driver-content
description: The KsQueryMediums method retrieves mediums that a pin supports.
old-location: stream\ikspin_ksquerymediums.htm
old-project: stream
ms.assetid: de6efd10-7f97-422a-abd4-c21c4cbc1dd7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsPin, IKsPin interface [Streaming Media Devices], KsQueryMediums method, IKsPin::KsQueryMediums, KsQueryMediums method [Streaming Media Devices], KsQueryMediums method [Streaming Media Devices], IKsPin interface, KsQueryMediums,IKsPin.KsQueryMediums, ksproxy/IKsPin::KsQueryMediums, ksproxy_88debe31-2dd5-41bc-80c0-164b28dc586f.xml, stream.ikspin_ksquerymediums
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
-	IKsPin.KsQueryMediums
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsPin::KsQueryMediums method


## -description


The <b>KsQueryMediums</b> method retrieves mediums that a pin supports. 


## -parameters




### -param MediumList [out]

Pointer to a buffer that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563441">KSMULTIPLE_ITEM</a> structure, followed by a sequence of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a> structures that describe medium types. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The returned mediums are ordered by preference. 

Applications call <b>KsQueryMediums</b> to retrieve mediums that pins support in order to build a filter graph.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563441">KSMULTIPLE_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPin::KsQueryMediums method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

