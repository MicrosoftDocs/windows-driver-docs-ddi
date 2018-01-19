---
UID: NS:avc._AVC_PIN_DESCRIPTOR
title: _AVC_PIN_DESCRIPTOR
author: windows-driver-content
description: The AVC_PIN_DESCRIPTOR structure describes a pin on an AV/C subunit device.
old-location: stream\avc_pin_descriptor.htm
old-project: stream
ms.assetid: 6d404c47-01ae-496c-8252-32f180cf0fd3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _AVC_PIN_DESCRIPTOR, AVC_PIN_DESCRIPTOR, *PAVC_PIN_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVC_PIN_DESCRIPTOR
req.alt-loc: avc.h
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
req.typenames: AVC_PIN_DESCRIPTOR, *PAVC_PIN_DESCRIPTOR
---

# _AVC_PIN_DESCRIPTOR structure



## -description
The AVC_PIN_DESCRIPTOR structure describes a pin on an AV/C subunit device.



## -syntax

````
typedef struct _AVC_PIN_DESCRIPTOR {
  ULONG                  PinId;
  KSPIN_DESCRIPTOR       PinDescriptor;
  PFNAVCINTERSECTHANDLER IntersectHandler;
  PVOID                  Context;
} AVC_PIN_DESCRIPTOR, *PAVC_PIN_DESCRIPTOR;
````


## -struct-fields

### -field PinId

Specifies the offset (or ID) of the pin for which information is to be retrieved.


### -field PinDescriptor

Specifies a KSPIN_DESCRIPTOR structure. This structure is allocated in the nonpaged pool. The subunit driver must not free this pointer.


### -field IntersectHandler

An optional output parameter specifying a data range intersect handler associated with the <b>DataRanges</b> member of the <b>PinDescriptor</b> member.


### -field Context

An optional output parameter specifying a value to be passed to the <b>IntersectHandler</b> when it is called during format negotiation. For more information about what an intersect handler is, see <a href="https://msdn.microsoft.com/44281574-8258-47a3-857d-fd44bb949f17">DataRange Intersections in AVStream</a>.


## -remarks
This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554160">AVC_FUNCTION_GET_PIN_DESCRIPTOR</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.

A description of the members of the <b>KSPIN_DESCRIPTOR</b> structure used in AVC_PIN_DESCRIPTOR follows:


## -see-also
<dl>
<dt>
<a href="..\avc\nc-avc-pfnavcintersecthandler.md">AV/C Intersect Handler</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_PIN_DESCRIPTOR structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

