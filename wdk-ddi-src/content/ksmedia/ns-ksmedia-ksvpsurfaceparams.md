---
UID: NS:ksmedia.KSVPSURFACEPARAMS
title: KSVPSURFACEPARAMS
author: windows-driver-content
description: The KSVPSURFACEPARAMS structure is used to describe the surface parameters of a video port surface.
old-location: stream\ksvpsurfaceparams.htm
old-project: stream
ms.assetid: 8a1ce43d-ba2c-489c-b37f-d98b9cf1d6b0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSVPSURFACEPARAMS, KSVPSURFACEPARAMS, KSVPSURFACEPARAMS structure [Streaming Media Devices], PKSVPSURFACEPARAMS, PKSVPSURFACEPARAMS structure pointer [Streaming Media Devices], dvdref_676b0467-3a23-4aac-8f72-7fd53ef399dd.xml, ksmedia/KSVPSURFACEPARAMS, ksmedia/PKSVPSURFACEPARAMS, stream.ksvpsurfaceparams"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSVPSURFACEPARAMS
product: Windows
targetos: Windows
req.typenames: KSVPSURFACEPARAMS, *PKSVPSURFACEPARAMS
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566509">KSPROPERTY_VPCONFIG_SURFACEPARAMS</a>



 

 


