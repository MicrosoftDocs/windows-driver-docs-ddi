---
UID: NS:ksmedia.KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
title: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
author: windows-driver-content
description: The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure specifies if interleaved capture is supported.
old-location: stream\ksproperty_allocator_control_capture_caps_s.htm
old-project: stream
ms.assetid: be13bf95-eae9-4ae4-b5f3-cc1bdf3acd02
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
req.alt-loc: ksmedia.h
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
req.typenames: *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
---

# KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure



## -description
The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure specifies if interleaved capture is supported.



## -syntax

````
typedef struct {
  ULONG InterleavedCapSupported;
} KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S;
````


## -struct-fields

### -field InterleavedCapSupported

Indicates whether interleaved capture is supported. Any nonzero value indicates that interleaved capture is supported. A value of zero indicates interleaved capture is not supported.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564267">KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567792">PROPSETID_ALLOCATOR_CONTROL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

