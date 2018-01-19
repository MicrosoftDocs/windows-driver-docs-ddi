---
UID: NS:ksmedia.KSVPSURFACEPARAMS
title: KSVPSURFACEPARAMS
author: windows-driver-content
description: The KSVPSURFACEPARAMS structure is used to describe the surface parameters of a video port surface.
old-location: stream\ksvpsurfaceparams.htm
old-project: stream
ms.assetid: 8a1ce43d-ba2c-489c-b37f-d98b9cf1d6b0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSVPSURFACEPARAMS, *PKSVPSURFACEPARAMS, KSVPSURFACEPARAMS
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
req.alt-api: KSVPSURFACEPARAMS
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
req.typenames: *PKSVPSURFACEPARAMS, KSVPSURFACEPARAMS
---

# KSVPSURFACEPARAMS structure



## -description
The KSVPSURFACEPARAMS structure is used to describe the surface parameters of a video port surface.



## -syntax

````
typedef struct {
  DWORD dwPitch;
  DWORD dwXOrigin;
  DWORD dwYOrigin;
} KSVPSURFACEPARAMS, *PKSVPSURFACEPARAMS;
````


## -struct-fields

### -field dwPitch

Specifies the pitch (byte count between subsequent lines) of the video port surface.


### -field dwXOrigin

Indicates the x-origin of the video port surface.


### -field dwYOrigin

Indicates the y-origin of the video port surface.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566509">KSPROPERTY_VPCONFIG_SURFACEPARAMS</a> property.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566509">KSPROPERTY_VPCONFIG_SURFACEPARAMS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSVPSURFACEPARAMS structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

