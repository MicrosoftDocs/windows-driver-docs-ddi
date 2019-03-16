---
UID: NN:ksproxy.IKsDataTypeCompletion
title: IKsDataTypeCompletion (ksproxy.h)
description: The IKsDataTypeCompletion interface provides a method to complete partially specified media types that are passed to the IAMStreamConfig::SetFormat method.
old-location: stream\iksdatatypecompletion.htm
tech.root: stream
ms.assetid: 52976c7d-522e-4ff6-96a2-8ed98abe1739
ms.date: 04/23/2018
ms.keywords: IKsDataTypeCompletion, IKsDataTypeCompletion interface [Streaming Media Devices], IKsDataTypeCompletion interface [Streaming Media Devices],described, ksproxy/IKsDataTypeCompletion, ksproxy_0ae81dab-7e72-45e0-9577-069d41973670.xml, stream.iksdatatypecompletion
ms.topic: interface
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsDataTypeCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsDataTypeCompletion interface


## -description


The <b>IKsDataTypeCompletion</b> interface provides a method to complete partially specified media types that are passed to the <b>IAMStreamConfig::SetFormat</b> method. 

The IID for this interface is IID_IKsDataTypeCompletion.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsDataTypeCompletion</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsDataTypeCompletion</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsDataTypeCompletion</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0a6157cf-09ae-4640-9c54-3e9b91fd93a9">KsCompleteMediaType</a>
</td>
<td align="left" width="63%">
Completes a partially specified media type.

</td>
</tr>
</table> 


## -remarks



In order to keep the proxy data type neutral, optional data type handlers can be loaded to massage the data stream as it passes to or from kernel-mode filters. You should implement a data type handler as a COM server that, at least, supports the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559807">IKsDataTypeHandler</a> interface. The <b>IKsDataTypeCompletion</b> interface is optional for data type handlers. A data type handler only supports <b>IKsDataTypeCompletion</b> if the media format has a partially specified form.

A data type handler is typically loaded during the pin connection process, and unloaded when the connection is broken. However, a data type handler is sometimes loaded briefly for other purposes. For instance, if an application uses DirectShow's <b>IAMStreamConfig::SetFormat</b> method, the application possibly uses a data type handler to complete a partial media type parameter returned from <b>IAMStreamConfig::SetFormat</b>. For more information about <b>IAMStreamConfig::SetFormat</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559807">IKsDataTypeHandler</a>
 

 

