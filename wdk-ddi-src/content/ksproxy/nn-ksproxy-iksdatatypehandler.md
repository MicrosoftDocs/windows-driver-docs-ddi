---
UID: NN:ksproxy.IKsDataTypeHandler
title: IKsDataTypeHandler (ksproxy.h)
description: The IKsDataTypeHandler interface provides methods that perform optional preprocessing and postprocessing of media samples.
tech.root: stream
ms.date: 06/11/2021
keywords: ["IKsDataTypeHandler interface"]
ms.keywords: IKsDataTypeHandler, IKsDataTypeHandler interface [Streaming Media Devices], IKsDataTypeHandler interface [Streaming Media Devices],described, ksproxy/IKsDataTypeHandler, ksproxy_fd2ab182-1556-438e-bc5e-fe1339d0d865.xml, stream.iksdatatypehandler
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
 - IKsDataTypeHandler
 - ksproxy/IKsDataTypeHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsDataTypeHandler
---

# IKsDataTypeHandler interface

## -description

The **IKsDataTypeHandler** interface provides methods that perform optional preprocessing and postprocessing of media samples. This interface also can return the size of extra stream header information that is required for processing and can determine if a particular media type is within a given set of kernel streaming data ranges.

The IID for this interface is IID_IKsDataTypeHandler.

## -inheritance

The **IKsDataTypeHandler** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

In order to keep the proxy data type neutral, optional data type handlers can be loaded to massage the data stream as it passes to or from kernel-mode filters. You should implement a data type handler as a COM server that, at least, supports the **IKsDataTypeHandler** interface. Your data type handler can optionally support the [IKsDataTypeCompletion](/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksdatatypecompletion) interface.

A data type handler is typically loaded during the pin connection process, and unloaded when the connection is broken. However, a data type handler is sometimes loaded briefly for other purposes. For instance, if an application uses DirectShow's **IAMStreamConfig::SetFormat** method, the application possibly uses a data type handler to complete a partial media type parameter sent to the method.

The proxy uses the GUIDs from the media type as COM server classes to determine what if any data type handler to load. As long as the data type handler is registered as a COM server under an expected GUID class that the proxy looks for, the data type handler is loaded. The major format type is first used to attempt to open a data type handler COM server, followed by the subtype and format specifier if opening the data type handler fails using the major format type. If any of the attempts succeed, the proxy queries for the **IKsDataTypeHandler** interface and calls the interface's **KsSetMediaType** method to establish the current media type being used with the handler, in case the handler supports many types. If no handler is found, then the proxy assumes none is necessary when marshaling the stream to or from kernel mode, or to perform any other tasks necessary.

On a data type handler create request through **CoCreateInstance**, the server is always presented an outer **IUnknown** with which to create the COM object. This **IUnknown** is an interface on the pin object that is loading this handler. The **IUnknown** interface pointer may be used to query information or interfaces from the pin, such as the **IKsPin** or **IKsControl** interfaces, although the kernel-mode pin may not have been created at the time the handler is loaded. No reference should be left on the outer object through acquiring any interfaces, as it will result in a circular reference count. Using the interfaces without a reference count is acceptable, because the outer object owns the handler and, by definition, is destroyed when the outer object's reference count reaches zero.

For more information about **IAMStreamConfig::SetFormat** and **CoCreateInstance**, see the Microsoft Windows SDK documentation.

## -see-also

[IKsDataTypeCompletion](/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksdatatypecompletion)
