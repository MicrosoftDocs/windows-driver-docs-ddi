---
UID: NN:ksproxy.IKsDataTypeHandler
title: IKsDataTypeHandler
author: windows-driver-content
description: The IKsDataTypeHandler interface provides methods that perform optional preprocessing and postprocessing of media samples.
old-location: stream\iksdatatypehandler.htm
old-project: stream
ms.assetid: ef08d375-1ac6-489f-9fd4-f791ce82c553
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsDataTypeHandler, IKsDataTypeHandler interface [Streaming Media Devices], IKsDataTypeHandler interface [Streaming Media Devices], described, ksproxy/IKsDataTypeHandler, ksproxy_fd2ab182-1556-438e-bc5e-fe1339d0d865.xml, stream.iksdatatypehandler
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: Ksproxy.lib
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
-	IKsDataTypeHandler
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsDataTypeHandler interface


## -description


The <b>IKsDataTypeHandler</b> interface provides methods that perform optional preprocessing and postprocessing of media samples. This interface also can return the size of extra stream header information that is required for processing and can determine if a particular media type is within a given set of kernel streaming data ranges. 

The IID for this interface is IID_IKsDataTypeHandler.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsDataTypeHandler</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsDataTypeHandler</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsDataTypeHandler</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/46a58007-16bf-422b-8408-30a7b65dbee6">KsCompleteIoOperation</a>
</td>
<td align="left" width="63%">
Cleans up the extended header and completes the I/O operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/354dcd2b-fa63-4574-94d8-149e3f199751">KsIsMediaTypeInRanges</a>
</td>
<td align="left" width="63%">
Validates that a media type is within specific data ranges.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/16411d58-5fff-430f-b96d-78eed1dbb01c">KsPrepareIoOperation</a>
</td>
<td align="left" width="63%">
Initializes the extended header and prepares the media sample for an I/O operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/14d03e6f-d02c-4b39-8f21-b339c65fb036">KsQueryExtendedSize</a>
</td>
<td align="left" width="63%">
Retrieves extended header information required for I/O operations.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b1c97d4f-b305-4c9f-b3fd-06d0ebcb0ed0">KsSetMediaType</a>
</td>
<td align="left" width="63%">
Sets the media type for a data handler.

</td>
</tr>
</table> 


## -remarks



In order to keep the proxy data type neutral, optional data type handlers can be loaded to massage the data stream as it passes to or from kernel-mode filters. You should implement a data type handler as a COM server that, at least, supports the <b>IKsDataTypeHandler</b> interface. Your data type handler can optionally support the <a href="..\ksproxy\nn-ksproxy-iksdatatypecompletion.md">IKsDataTypeCompletion</a> interface. 

A data type handler is typically loaded during the pin connection process, and unloaded when the connection is broken. However, a data type handler is sometimes loaded briefly for other purposes. For instance, if an application uses DirectShow's <b>IAMStreamConfig::SetFormat</b> method, the application possibly uses a data type handler to complete a partial media type parameter sent to the method. 

The proxy uses the GUIDs from the media type as COM server classes to determine what if any data type handler to load. As long as the data type handler is registered as a COM server under an expected GUID class that the proxy looks for, the data type handler is loaded. The major format type is first used to attempt to open a data type handler COM server, followed by the subtype and format specifier if opening the data type handler fails using the major format type. If any of the attempts succeed, the proxy queries for the <b>IKsDataTypeHandler</b> interface and calls the interface's <b>KsSetMediaType</b> method to establish the current media type being used with the handler, in case the handler supports many types. If no handler is found, then the proxy assumes none is necessary when marshaling the stream to or from kernel mode, or to perform any other tasks necessary.

On a data type handler create request through <b>CoCreateInstance</b>, the server is always presented an outer <b>IUnknown</b> with which to create the COM object. This <b>IUnknown</b> is an interface on the pin object that is loading this handler. The <b>IUnknown</b> interface pointer may be used to query information or interfaces from the pin, such as the <b>IKsPin</b> or <b>IKsControl</b> interfaces, although the kernel-mode pin may not have been created at the time the handler is loaded. No reference should be left on the outer object through acquiring any interfaces, as it will result in a circular reference count. Using the interfaces without a reference count is acceptable, because the outer object owns the handler and, by definition, is destroyed when the outer object's reference count reaches zero.

For more information about <b>IAMStreamConfig::SetFormat</b> and <b>CoCreateInstance</b>, see the Microsoft Windows SDK documentation.




## -see-also

<a href="..\ksproxy\nn-ksproxy-iksdatatypecompletion.md">IKsDataTypeCompletion</a>



 

 


