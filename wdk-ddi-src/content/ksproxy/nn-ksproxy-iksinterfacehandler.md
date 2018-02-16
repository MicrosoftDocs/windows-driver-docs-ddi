---
UID: NN:ksproxy.IKsInterfaceHandler
title: IKsInterfaceHandler
author: windows-driver-content
description: The IKsInterfaceHandler interface provides methods that marshal samples into the kernel based on the KSPIN_INTERFACE structure specified for the established connection. The IID for this interface is IID_IKsInterfaceHandler.
old-location: stream\iksinterfacehandler.htm
old-project: stream
ms.assetid: b9f72e79-930c-456e-8001-5df808604caa
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.iksinterfacehandler, IKsInterfaceHandler interface [Streaming Media Devices], IKsInterfaceHandler interface [Streaming Media Devices], described, IKsInterfaceHandler, ksproxy/IKsInterfaceHandler, ksproxy_9d597bae-a5d7-4575-a4ac-983b827b0ae4.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsInterfaceHandler
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsInterfaceHandler interface


## -description


The <b>IKsInterfaceHandler</b> interface provides methods that marshal samples into the kernel based on the <a href="..\ks\ns-ks-ksidentifier.md">KSPIN_INTERFACE</a> structure specified for the established connection. The IID for this interface is IID_IKsInterfaceHandler.


## -members

The <b>IKsInterfaceHandler</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2ff69f59-5fbd-43fd-afe5-9717d7928d2a">KsCompleteIo</a>
</td>
<td align="left" width="63%">
Cleans up extended headers and releases media samples. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/3f0982d8-4ac3-40f6-8587-624c26d25510">KsProcessMediaSamples</a>
</td>
<td align="left" width="63%">
Queries for the extended header size if a data handler is specified. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/71e4be0a-a5a6-469a-948b-bc5277bc8cbe">KsSetPin</a>
</td>
<td align="left" width="63%">
Informs an interface handler about the pin with which to communicate when passing data.

</td>
</tr>
</table>Cleans up extended headers and releases media samples. 

Queries for the extended header size if a data handler is specified. 

Informs an interface handler about the pin with which to communicate when passing data.

 


## -remarks



In order to keep the proxy neutral with regard to the interface used to stream data, interface handlers are loaded to translate DirectShow media samples to and from a kernel-level driver. An interface handler implements the methods of the <b>IKsInterfaceHandler</b> interface to perform preprocessing and postprocessing on all media samples and to signal the completion of input and output (I/O).

Each interface handler can marshal media samples using its own method. The standard interface handler that KS proxy implements uses IOCTL_KS_WRITE_STREAM for the receive operation and IOCTL_KS_READ_STREAM for the send operation, but a custom interface handler can use some other method.

When a pin is connected, the proxy uses the GUID in the <b>Set</b> member of the <a href="..\ks\ns-ks-ksidentifier.md">KSPIN_INTERFACE</a> structure to determine what interface handler to load. The interface handler is registered as a COM server under that GUID class. The interface handler must handle all variations of the interface within the interface set. Bridge pins are not expected to stream data, and interface handlers are not loaded for them.

On an interface handler create request through <b>CoCreateInstance</b>, the server is always presented an outer <b>IUnknown</b> with which to create the COM object. This <b>IUnknown</b> is an interface on the pin object that is loading this interface handler. The <b>IUnknown</b> interface pointer can be used to query information or interfaces, such as the <b>IKsControl</b> interface, from the pin, although the kernel-mode pin may not have been created at the time the interface handler is loaded. No reference should be left on the outer object through acquiring any interfaces, as it will result in a circular reference count. Using the interfaces without a reference count is acceptable, because the outer object owns the handler and, by definition, is destroyed when the outer object's reference count reaches zero.

For more information about <b>CoCreateInstance</b>, see the Microsoft Windows SDK documentation.




## -see-also

<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>



<a href="..\ks\ns-ks-ksidentifier.md">KSPIN_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsInterfaceHandler interface%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

