---
UID: NN:ksproxy.IKsPin
title: IKsPin (ksproxy.h)
description: The IKsPin interface provides methods that control and retrieve information about a pin.
tech.root: stream
ms.date: 06/11/2021
keywords: ["IKsPin interface"]
ms.keywords: IKsPin, IKsPin interface [Streaming Media Devices], IKsPin interface [Streaming Media Devices],described, ksproxy/IKsPin, ksproxy_9a020f8a-1271-47ea-816f-1132e44b6f45.xml, stream.ikspin
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsPin
 - ksproxy/IKsPin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPin
---

# IKsPin interface

## -description

The **IKsPin** interface provides methods that control and retrieve information about a pin.

The IID for this interface is IID_IKsPin.

## -inheritance

The **IKsPin** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

An interface handler ([IKsInterfaceHandler](./nn-ksproxy-iksinterfacehandler.md)) uses many of the **IKsPin** methods to route media samples of a particular media type.

## -see-also

[IKsInterfaceHandler](./nn-ksproxy-iksinterfacehandler.md)