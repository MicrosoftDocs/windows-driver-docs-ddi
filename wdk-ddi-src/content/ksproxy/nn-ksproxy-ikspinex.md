---
UID: NN:ksproxy.IKsPinEx
title: IKsPinEx (ksproxy.h)
description: The IKsPinEx interface inherits all the methods of the IKsPin interface and extends IKsPin to provide a method that notifies the filter graph of an error to give the filter graph an opportunity to halt.
tech.root: stream
ms.date: 06/11/2021
keywords: ["IKsPinEx interface"]
ms.keywords: IKsPinEx, IKsPinEx interface [Streaming Media Devices], IKsPinEx interface [Streaming Media Devices],described, ksproxy/IKsPinEx, ksproxy_3c92d570-f22f-4165-bafd-9a22f5516137.xml, stream.ikspinex
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsPinEx
 - ksproxy/IKsPinEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Ksproxy.lib
 - Ksproxy.dll
api_name:
 - IKsPinEx
---

# IKsPinEx interface

## -description

The **IKsPinEx** interface inherits all the methods of the **IKsPin** interface and extends **IKsPin** to provide a method that notifies the filter graph of an error to give the filter graph an opportunity to halt.

The IID for this interface is IID_IKsPinEx.

## -inheritance

The **IKsPinEx** interface inherits from [IKsPin](./nn-ksproxy-ikspin.md).

## -remarks

An interface handler ([IKsInterfaceHandler](./nn-ksproxy-iksinterfacehandler.md)) uses many of the **IKsPinEx** methods to route media samples of a particular media type.

## -see-also

[IKsInterfaceHandler](./nn-ksproxy-iksinterfacehandler.md)

[IKsPin](./nn-ksproxy-ikspin.md)