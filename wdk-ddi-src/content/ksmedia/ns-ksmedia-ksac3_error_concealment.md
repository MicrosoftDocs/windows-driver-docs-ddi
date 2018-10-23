---
UID: NS:ksmedia.KSAC3_ERROR_CONCEALMENT
title: KSAC3_ERROR_CONCEALMENT
author: windows-driver-content
description: The KSAC3_ERROR_CONCEALMENT structure specifies how errors in an AC-3-encoded stream should be concealed during playback.
old-location: audio\ksac3_error_concealment.htm
tech.root: audio
ms.assetid: 1ef69cb7-2437-4ab4-8727-b7718a3adbb1
ms.date: 05/08/2018
ms.keywords: "*PKSAC3_ERROR_CONCEALMENT, KSAC3_ERROR_CONCEALMENT, KSAC3_ERROR_CONCEALMENT structure [Audio Devices], PKSAC3_ERROR_CONCEALMENT, PKSAC3_ERROR_CONCEALMENT structure pointer [Audio Devices], aud-prop_c5ba7732-b759-4110-8d43-bc4d5b351c6e.xml, audio.ksac3_error_concealment, ksmedia/KSAC3_ERROR_CONCEALMENT, ksmedia/PKSAC3_ERROR_CONCEALMENT"
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
-	KSAC3_ERROR_CONCEALMENT
product:
- Windows
targetos: Windows
req.typenames: KSAC3_ERROR_CONCEALMENT, *PKSAC3_ERROR_CONCEALMENT
---

# KSAC3_ERROR_CONCEALMENT structure


## -description


The KSAC3_ERROR_CONCEALMENT structure specifies how errors in an AC-3-encoded stream should be concealed during playback.


## -struct-fields




### -field fRepeatPreviousBlock

Specifies whether to repeat the previous block when an error occurs. If <b>TRUE</b>, the decoder repeats the last block not in error as long as errors are detected in the input stream. If <b>FALSE</b>, the decoder mutes. A muted output stream does not necessarily result in any data packets. Instead, the renderer might substitute a more reliable stream or simply output silence.


### -field fErrorInCurrentBlock

Specifies whether the current block contains an error. If <b>TRUE</b>, the current block contains an error. If <b>FALSE</b>, the current block has no errors.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537220">KSPROPERTY_AC3_ERROR_CONCEALMENT</a> property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537220">KSPROPERTY_AC3_ERROR_CONCEALMENT</a>
 

 

