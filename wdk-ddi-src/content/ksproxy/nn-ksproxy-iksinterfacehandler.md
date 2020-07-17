---
UID: NN:ksproxy.IKsInterfaceHandler
title: IKsInterfaceHandler (ksproxy.h)
description: The IKsInterfaceHandler interface provides methods that marshal samples into the kernel based on the KSPIN_INTERFACE structure specified for the established connection. The IID for this interface is IID_IKsInterfaceHandler.
old-location: stream\iksinterfacehandler.htm
tech.root: stream
ms.assetid: b9f72e79-930c-456e-8001-5df808604caa
ms.date: 04/23/2018
keywords: ["IKsInterfaceHandler interface"]
ms.keywords: IKsInterfaceHandler, IKsInterfaceHandler interface [Streaming Media Devices], IKsInterfaceHandler interface [Streaming Media Devices],described, ksproxy/IKsInterfaceHandler, ksproxy_9d597bae-a5d7-4575-a4ac-983b827b0ae4.xml, stream.iksinterfacehandler
f1_keywords:
 - "ksproxy/IKsInterfaceHandler"
 - "IKsInterfaceHandler"
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
- IKsInterfaceHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsInterfaceHandler interface

## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IKsInterfaceHandler</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IKsInterfaceHandler</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -description


The <b>IKsInterfaceHandler</b> interface provides methods that marshal samples into the kernel based on the <a href="https://docs.microsoft.com/previous-versions/ff563537(v=vs.85)">KSPIN_INTERFACE</a> structure specified for the established connection. The IID for this interface is IID_IKsInterfaceHandler.



## -remarks



In order to keep the proxy neutral with regard to the interface used to stream data, interface handlers are loaded to translate DirectShow media samples to and from a kernel-level driver. An interface handler implements the methods of the <b>IKsInterfaceHandler</b> interface to perform preprocessing and postprocessing on all media samples and to signal the completion of input and output (I/O).

Each interface handler can marshal media samples using its own method. The standard interface handler that KS proxy implements uses IOCTL_KS_WRITE_STREAM for the receive operation and IOCTL_KS_READ_STREAM for the send operation, but a custom interface handler can use some other method.

When a pin is connected, the proxy uses the GUID in the <b>Set</b> member of the <a href="https://docs.microsoft.com/previous-versions/ff563537(v=vs.85)">KSPIN_INTERFACE</a> structure to determine what interface handler to load. The interface handler is registered as a COM server under that GUID class. The interface handler must handle all variations of the interface within the interface set. Bridge pins are not expected to stream data, and interface handlers are not loaded for them.

On an interface handler create request through <b>CoCreateInstance</b>, the server is always presented an outer <b>IUnknown</b> with which to create the COM object. This <b>IUnknown</b> is an interface on the pin object that is loading this interface handler. The <b>IUnknown</b> interface pointer can be used to query information or interfaces, such as the <b>IKsControl</b> interface, from the pin, although the kernel-mode pin may not have been created at the time the interface handler is loaded. No reference should be left on the outer object through acquiring any interfaces, as it will result in a circular reference count. Using the interfaces without a reference count is acceptable, because the outer object owns the handler and, by definition, is destroyed when the outer object's reference count reaches zero.

For more information about <b>CoCreateInstance</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a>



<a href="https://docs.microsoft.com/previous-versions/ff563537(v=vs.85)">KSPIN_INTERFACE</a>
 

 

