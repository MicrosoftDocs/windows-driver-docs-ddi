---
UID: NN:ksproxy.IKsObject
title: IKsObject (ksproxy.h)
description: The IKsObject interface provides a method to retrieve the file handle of a KS object.
tech.root: stream
ms.date: 06/11/2021
keywords: ["IKsObject interface"]
ms.keywords: IKsObject, IKsObject interface [Streaming Media Devices], IKsObject interface [Streaming Media Devices],described, ksproxy_6432effa-13f1-4b39-a158-c315a93108d4.xml, stream.iksobject
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
req.lib: Ksproxy.h
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsObject
 - ksproxy/IKsObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
 - ksproxy.h.dll
api_name:
 - IKsObject
---

# IKsObject interface

## -description

The **IKsObject** interface provides a method to retrieve the file handle of a KS object.

## -inheritance

The **IKsObject** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

The IID for this interface is IID_IKsObject.

**IKsObject** is defined in *Ksproxy.h* within the `#ifdef __STREAMS__` section.

`__STREAMS__` is defined in *Stream.h*, a header from the DirectX SDK.
