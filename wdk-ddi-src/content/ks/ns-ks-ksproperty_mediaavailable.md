---
UID: NS:ks.KSPROPERTY_MEDIAAVAILABLE
title: KSPROPERTY_MEDIAAVAILABLE
author: windows-driver-content
description: The KSPROPERTY_MEDIAAVAILABLE structure specifies the media time span (the time span that a client can seek within) that is currently available on a filter.
old-location: stream\ksproperty_mediaavailable.htm
old-project: stream
ms.assetid: b6818fd5-e351-4eac-a802-af8229b82fb3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KSPROPERTY_MEDIAAVAILABLE structure [Streaming Media Devices], stream.ksproperty_mediaavailable, PKSPROPERTY_MEDIAAVAILABLE, ks-struct_bb14a2ee-bf9b-4a73-ae35-967aea3d7086.xml, PKSPROPERTY_MEDIAAVAILABLE structure pointer [Streaming Media Devices], KSPROPERTY_MEDIAAVAILABLE, *PKSPROPERTY_MEDIAAVAILABLE, ks/KSPROPERTY_MEDIAAVAILABLE, ks/PKSPROPERTY_MEDIAAVAILABLE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_MEDIAAVAILABLE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

