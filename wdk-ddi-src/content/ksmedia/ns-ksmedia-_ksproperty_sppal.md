---
UID: NS:ksmedia._KSPROPERTY_SPPAL
title: "_KSPROPERTY_SPPAL"
author: windows-driver-content
description: The KSPROPERTY_SPPAL structure is used to describe the palette of a subpicture display.
old-location: stream\ksproperty_sppal.htm
old-project: stream
ms.assetid: b6c50f2f-efc7-415f-895b-fcffb2575fe8
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_SPPAL, KSPROPERTY_SPPAL, KSPROPERTY_SPPAL structure [Streaming Media Devices], PKSPROPERTY_SPPAL, PKSPROPERTY_SPPAL structure pointer [Streaming Media Devices], _KSPROPERTY_SPPAL, dvdref_002f96c4-a499-4f93-8c3a-b083ed7a3339.xml, ksmedia/KSPROPERTY_SPPAL, ksmedia/PKSPROPERTY_SPPAL, stream.ksproperty_sppal"
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
-	KSPROPERTY_SPPAL
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_SPPAL, *PKSPROPERTY_SPPAL
---

# _KSPROPERTY_SPPAL structure


## -description


The KSPROPERTY_SPPAL structure is used to describe the palette of a subpicture display.


## -struct-fields




### -field sppal

Specifies an array of 16 YUV color values.


## -remarks



The KSPROPERTY_SPPAL structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565151">KSPROPERTY_DVDSUBPIC_PALETTE</a> property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565151">KSPROPERTY_DVDSUBPIC_PALETTE</a>
 

 

