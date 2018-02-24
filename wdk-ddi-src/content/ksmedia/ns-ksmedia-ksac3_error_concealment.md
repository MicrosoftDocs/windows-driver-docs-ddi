---
UID: NS:ksmedia.KSAC3_ERROR_CONCEALMENT
title: KSAC3_ERROR_CONCEALMENT
author: windows-driver-content
description: The KSAC3_ERROR_CONCEALMENT structure specifies how errors in an AC-3-encoded stream should be concealed during playback.
old-location: audio\ksac3_error_concealment.htm
old-project: audio
ms.assetid: 1ef69cb7-2437-4ab4-8727-b7718a3adbb1
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: PKSAC3_ERROR_CONCEALMENT structure pointer [Audio Devices], KSAC3_ERROR_CONCEALMENT structure [Audio Devices], KSAC3_ERROR_CONCEALMENT, PKSAC3_ERROR_CONCEALMENT, ksmedia/PKSAC3_ERROR_CONCEALMENT, ksmedia/KSAC3_ERROR_CONCEALMENT, aud-prop_c5ba7732-b759-4110-8d43-bc4d5b351c6e.xml, audio.ksac3_error_concealment, *PKSAC3_ERROR_CONCEALMENT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSAC3_ERROR_CONCEALMENT
product: Windows
targetos: Windows
req.typenames: KSAC3_ERROR_CONCEALMENT, *PKSAC3_ERROR_CONCEALMENT
---

# KSAC3_ERROR_CONCEALMENT structure


## -description


The KSAC3_ERROR_CONCEALMENT structure specifies how errors in an AC-3-encoded stream should be concealed during playback.


## -syntax


````
typedef struct {
  BOOL fRepeatPreviousBlock;
  BOOL fErrorInCurrentBlock;
} KSAC3_ERROR_CONCEALMENT, *PKSAC3_ERROR_CONCEALMENT;
````


## -struct-fields




### -field fRepeatPreviousBlock

Specifies whether to repeat the previous block when an error occurs. If <b>TRUE</b>, the decoder repeats the last block not in error as long as errors are detected in the input stream. If <b>FALSE</b>, the decoder mutes. A muted output stream does not necessarily result in any data packets. Instead, the renderer might substitute a more reliable stream or simply output silence.


### -field fErrorInCurrentBlock

Specifies whether the current block contains an error. If <b>TRUE</b>, the current block contains an error. If <b>FALSE</b>, the current block has no errors.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537220">KSPROPERTY_AC3_ERROR_CONCEALMENT</a> property.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537220">KSPROPERTY_AC3_ERROR_CONCEALMENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAC3_ERROR_CONCEALMENT structure%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

