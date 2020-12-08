---
UID: NN:ksproxy.IKsDataTypeCompletion
title: IKsDataTypeCompletion (ksproxy.h)
description: The IKsDataTypeCompletion interface provides a method to complete partially specified media types that are passed to the IAMStreamConfig::SetFormat method.
old-location: stream\iksdatatypecompletion.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsDataTypeCompletion interface"]
ms.keywords: IKsDataTypeCompletion, IKsDataTypeCompletion interface [Streaming Media Devices], IKsDataTypeCompletion interface [Streaming Media Devices],described, ksproxy/IKsDataTypeCompletion, ksproxy_0ae81dab-7e72-45e0-9577-069d41973670.xml, stream.iksdatatypecompletion
req.header: ksproxy.h
req.include-header: 
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

The <b>IKsDataTypeCompletion</b> interface provides a method to complete partially specified media types that are passed to the <b>IAMStreamConfig::SetFormat</b> method. 

The IID for this interface is IID_IKsDataTypeCompletion.

## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IKsDataTypeCompletion</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IKsDataTypeCompletion</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

In order to keep the proxy data type neutral, optional data type handlers can be loaded to massage the data stream as it passes to or from kernel-mode filters. You should implement a data type handler as a COM server that, at least, supports the <a href="/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksdatatypehandler">IKsDataTypeHandler</a> interface. The <b>IKsDataTypeCompletion</b> interface is optional for data type handlers. A data type handler only supports <b>IKsDataTypeCompletion</b> if the media format has a partially specified form.

A data type handler is typically loaded during the pin connection process, and unloaded when the connection is broken. However, a data type handler is sometimes loaded briefly for other purposes. For instance, if an application uses DirectShow's <b>IAMStreamConfig::SetFormat</b> method, the application possibly uses a data type handler to complete a partial media type parameter returned from <b>IAMStreamConfig::SetFormat</b>. For more information about <b>IAMStreamConfig::SetFormat</b>, see the Microsoft Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksdatatypehandler">IKsDataTypeHandler</a>
