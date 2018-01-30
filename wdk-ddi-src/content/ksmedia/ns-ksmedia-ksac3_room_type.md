---
UID: NS:ksmedia.KSAC3_ROOM_TYPE
title: KSAC3_ROOM_TYPE
author: windows-driver-content
description: The KSAC3_ROOM_TYPE structure specifies the type of audio mixing room in which an AC-3-encoded stream was produced.
old-location: audio\ksac3_room_type.htm
old-project: audio
ms.assetid: adf514e1-5413-4552-b676-7567e8fa9954
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ksmedia/KSAC3_ROOM_TYPE, KSAC3_ROOM_TYPE, PKSAC3_ROOM_TYPE structure pointer [Audio Devices], *PKSAC3_ROOM_TYPE, PKSAC3_ROOM_TYPE, aud-prop_cfc30aae-0335-42d9-bd6d-7888fed060af.xml, ksmedia/PKSAC3_ROOM_TYPE, KSAC3_ROOM_TYPE structure [Audio Devices], audio.ksac3_room_type
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
req.idl: KeywordDetectorOemAdapter.idl
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
-	ksmedia.h
apiname:
-	KSAC3_ROOM_TYPE
product: Windows
targetos: Windows
req.typenames: "*PKSAC3_ROOM_TYPE, KSAC3_ROOM_TYPE"
---

# KSAC3_ROOM_TYPE structure


## -description


The KSAC3_ROOM_TYPE structure specifies the type of audio mixing room in which an AC-3-encoded stream was produced.


## -syntax


````
typedef struct {
  BOOL fLargeRoom;
} KSAC3_ROOM_TYPE, *PKSAC3_ROOM_TYPE;
````


## -struct-fields




### -field fLargeRoom

Specifies the type and calibration of the mixing room used for the final audio mixing session. If <b>TRUE</b>, a large room with an X curve (described in the AC-3 specification; for more information, see the following Remarks section) was used. If <b>FALSE</b>, a small room with a flat curve was used.


## -remarks


This structure characterizes the production environment of an AC-3-encoded stream. The information in the structure is not typically used by the decoder, but might be used by other audio components after decoding.

This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537225">KSPROPERTY_AC3_ROOM_TYPE</a> property.

For more information about room types, see the AC-3 specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8730">Dolby Laboratories</a> website. The specification is titled Digital Audio Compression Standard (AC-3).



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537225">KSPROPERTY_AC3_ROOM_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAC3_ROOM_TYPE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

