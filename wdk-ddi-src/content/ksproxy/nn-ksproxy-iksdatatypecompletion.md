---
UID: NN:ksproxy.IKsDataTypeCompletion
title: IKsDataTypeCompletion (ksproxy.h)
description: The IKsDataTypeCompletion interface provides a method to complete partially specified media types that are passed to the IAMStreamConfig::SetFormat method.
tech.root: stream
ms.date: 06/11/2021
keywords: ["IKsDataTypeCompletion interface"]
ms.keywords: IKsDataTypeCompletion, IKsDataTypeCompletion interface [Streaming Media Devices], IKsDataTypeCompletion interface [Streaming Media Devices],described, ksproxy/IKsDataTypeCompletion, ksproxy_0ae81dab-7e72-45e0-9577-069d41973670.xml, stream.iksdatatypecompletion
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
 - IKsDataTypeCompletion
 - ksproxy/IKsDataTypeCompletion
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsDataTypeCompletion
---

# IKsDataTypeCompletion interface

## -description

The **IKsDataTypeCompletion** interface provides a method to complete partially specified media types that are passed to the **IAMStreamConfig::SetFormat** method.

The IID for this interface is IID_IKsDataTypeCompletion.

## -inheritance

The **IKsDataTypeCompletion** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

In order to keep the proxy data type neutral, optional data type handlers can be loaded to massage the data stream as it passes to or from kernel-mode filters. You should implement a data type handler as a COM server that, at least, supports the [IKsDataTypeHandler](./nn-ksproxy-iksdatatypehandler.md) interface. The **IKsDataTypeCompletion** interface is optional for data type handlers. A data type handler only supports **IKsDataTypeCompletion** if the media format has a partially specified form.

A data type handler is typically loaded during the pin connection process, and unloaded when the connection is broken. However, a data type handler is sometimes loaded briefly for other purposes. For instance, if an application uses DirectShow's **IAMStreamConfig::SetFormat** method, the application possibly uses a data type handler to complete a partial media type parameter returned from **IAMStreamConfig::SetFormat**. For more information about **IAMStreamConfig::SetFormat**, see the Microsoft Windows SDK documentation.

## -see-also

[IKsDataTypeHandler](./nn-ksproxy-iksdatatypehandler.md)