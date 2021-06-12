---
UID: NN:ksproxy.IKsInterfaceHandler
title: IKsInterfaceHandler (ksproxy.h)
description: The IKsInterfaceHandler interface provides methods that marshal samples into the kernel based on the KSPIN_INTERFACE structure specified for the established connection. The IID for this interface is IID_IKsInterfaceHandler.
tech.root: stream
ms.date: 06/11/2021
keywords: ["IKsInterfaceHandler interface"]
ms.keywords: IKsInterfaceHandler, IKsInterfaceHandler interface [Streaming Media Devices], IKsInterfaceHandler interface [Streaming Media Devices],described, ksproxy/IKsInterfaceHandler, ksproxy_9d597bae-a5d7-4575-a4ac-983b827b0ae4.xml, stream.iksinterfacehandler
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
 - IKsInterfaceHandler
 - ksproxy/IKsInterfaceHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsInterfaceHandler
---

# IKsInterfaceHandler interface

## -description

The **IKsInterfaceHandler** interface provides methods that marshal samples into the kernel based on the [KSPIN_INTERFACE](/previous-versions/ff563537(v=vs.85)) structure specified for the established connection. The IID for this interface is IID_IKsInterfaceHandler.

## -inheritance

The **IKsInterfaceHandler** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

In order to keep the proxy neutral with regard to the interface used to stream data, interface handlers are loaded to translate DirectShow media samples to and from a kernel-level driver. An interface handler implements the methods of the **IKsInterfaceHandler** interface to perform preprocessing and postprocessing on all media samples and to signal the completion of input and output (I/O).

Each interface handler can marshal media samples using its own method. The standard interface handler that KS proxy implements uses IOCTL_KS_WRITE_STREAM for the receive operation and IOCTL_KS_READ_STREAM for the send operation, but a custom interface handler can use some other method.

When a pin is connected, the proxy uses the GUID in the **Set** member of the [KSPIN_INTERFACE](/previous-versions/ff563537(v=vs.85)) structure to determine what interface handler to load. The interface handler is registered as a COM server under that GUID class. The interface handler must handle all variations of the interface within the interface set. Bridge pins are not expected to stream data, and interface handlers are not loaded for them.

On an interface handler create request through [**CoCreateInstance**](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance), the server is always presented an outer **IUnknown** with which to create the COM object. This **IUnknown** is an interface on the pin object that is loading this interface handler. The **IUnknown** interface pointer can be used to query information or interfaces, such as the **IKsControl** interface, from the pin, although the kernel-mode pin may not have been created at the time the interface handler is loaded. No reference should be left on the outer object through acquiring any interfaces, as it will result in a circular reference count. Using the interfaces without a reference count is acceptable, because the outer object owns the handler and, by definition, is destroyed when the outer object's reference count reaches zero.

## -see-also

[CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)

[IKsControl](/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol)

[KSPIN_INTERFACE](/previous-versions/ff563537(v=vs.85))
