---
UID: NF:ksproxy.IKsPin.KsPropagateAcquire
title: IKsPin::KsPropagateAcquire
author: windows-driver-content
description: The KsPropagateAcquire method directs all the pins on the filter to attain the Acquire state.
old-location: stream\ikspin_kspropagateacquire.htm
tech.root: stream
ms.assetid: 059bef5a-1db7-4fd7-a19b-c34df81f4447
ms.date: 4/23/2018
ms.keywords: IKsPin interface [Streaming Media Devices],KsPropagateAcquire method, IKsPin.KsPropagateAcquire, IKsPin::KsPropagateAcquire, KsPropagateAcquire, KsPropagateAcquire method [Streaming Media Devices], KsPropagateAcquire method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsPropagateAcquire, ksproxy_c3ce0cef-0366-4233-afa5-723f9d3bb4e9.xml, stream.ikspin_kspropagateacquire
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
-	IKsPin.KsPropagateAcquire
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPin::KsPropagateAcquire


## -description


The <b>KsPropagateAcquire</b> method directs all the pins on the filter to attain the Acquire state. 


## -parameters






## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



By using this method, a Communication source pin can direct the sink to which it is connected to change state before the Source. This forces the entire filter to which the sink belongs to change state so that any Acquire can be further propagated if needed.

This method is for proxy use and is not recommended for application use.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559896">IKsPin</a>
 

 

