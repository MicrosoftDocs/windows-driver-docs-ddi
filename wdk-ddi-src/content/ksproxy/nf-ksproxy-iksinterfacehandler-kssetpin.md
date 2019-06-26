---
UID: NF:ksproxy.IKsInterfaceHandler.KsSetPin
title: IKsInterfaceHandler::KsSetPin (ksproxy.h)
description: The KsSetPin method informs the streaming interface handler about the pin with which to communicate when passing data.
old-location: stream\iksinterfacehandler_kssetpin.htm
tech.root: stream
ms.assetid: 71e4be0a-a5a6-469a-948b-bc5277bc8cbe
ms.date: 04/23/2018
ms.keywords: IKsInterfaceHandler interface [Streaming Media Devices],KsSetPin method, IKsInterfaceHandler.KsSetPin, IKsInterfaceHandler::KsSetPin, KsSetPin, KsSetPin method [Streaming Media Devices], KsSetPin method [Streaming Media Devices],IKsInterfaceHandler interface, ksproxy/IKsInterfaceHandler::KsSetPin, ksproxy_3746aba4-11e3-45a5-8495-eda1cad5bf9b.xml, stream.iksinterfacehandler_kssetpin
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
- IKsInterfaceHandler.KsSetPin
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsInterfaceHandler::KsSetPin


## -description


The <b>KsSetPin</b> method informs the streaming interface handler about the pin with which to communicate when passing data.


## -parameters




### -param KsPin [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-ikspin">IKsPin</a> interface for the pin to which this streaming interface handler is to be attached. This pin must support the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksobject">IKsObject</a> interface from which the underlying kernel handle can be obtained.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The <b>KsSetPin</b> method is called after an instance of the interface handler is created but before any streaming is required of the instance.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksobject">IKsObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-ikspin">IKsPin</a>
 

 

