---
UID: NS:ks.KSPROPERTY_MEDIAAVAILABLE
title: KSPROPERTY_MEDIAAVAILABLE
author: windows-driver-content
description: The KSPROPERTY_MEDIAAVAILABLE structure specifies the media time span (the time span that a client can seek within) that is currently available on a filter.
old-location: stream\ksproperty_mediaavailable.htm
old-project: stream
ms.assetid: b6818fd5-e351-4eac-a802-af8229b82fb3
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_MEDIAAVAILABLE, KSPROPERTY_MEDIAAVAILABLE, KSPROPERTY_MEDIAAVAILABLE structure [Streaming Media Devices], PKSPROPERTY_MEDIAAVAILABLE, PKSPROPERTY_MEDIAAVAILABLE structure pointer [Streaming Media Devices], ks-struct_bb14a2ee-bf9b-4a73-ae35-967aea3d7086.xml, ks/KSPROPERTY_MEDIAAVAILABLE, ks/PKSPROPERTY_MEDIAAVAILABLE, stream.ksproperty_mediaavailable"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSPROPERTY_MEDIAAVAILABLE
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_MEDIAAVAILABLE, *PKSPROPERTY_MEDIAAVAILABLE
---

# KSPROPERTY_MEDIAAVAILABLE structure


## -description


The KSPROPERTY_MEDIAAVAILABLE structure specifies the media time span (the time span that a client can seek within) that is currently available on a filter. KSPROPERTY_MEDIAAVAILABLE is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565179">KSPROPERTY_MEDIASEEKING_AVAILABLE</a> property request.


## -syntax


````
typedef struct {
  LONGLONG Earliest;
  LONGLONG Latest;
} KSPROPERTY_MEDIAAVAILABLE, *PKSPROPERTY_MEDIAAVAILABLE;
````


## -struct-fields




### -field Earliest

Pointer to a variable that receives the earliest time for efficient seeking.


### -field Latest

Pointer to a variable that receives the latest time for efficient seeking.


## -remarks



This structure corresponds with DirectShow's <b>IMediaSeeking::GetAvailable</b>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565179">KSPROPERTY_MEDIASEEKING_AVAILABLE</a>



 

 


