---
UID: NE:ksmedia.AUDIO_CURVE_TYPE
title: AUDIO_CURVE_TYPE
author: windows-driver-content
description: The AUDIO_CURVE_TYPE enumeration defines constants that specify a curve algorithm to be applied to set a volume level.
old-location: audio\audio_curve_type.htm
old-project: audio
ms.assetid: E3CE3385-8744-4E3F-A5EF-41AC4E3E4375
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.audio_curve_type, AUDIO_CURVE_TYPE_WINDOWS_FADE, AUDIO_CURVE_TYPE, ksmedia/AUDIO_CURVE_TYPE, AUDIO_CURVE_TYPE_NONE, AUDIO_CURVE_TYPE enumeration [Audio Devices], ksmedia/AUDIO_CURVE_TYPE_NONE, ksmedia/AUDIO_CURVE_TYPE_WINDOWS_FADE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
-	Ksmedia.h
apiname:
-	AUDIO_CURVE_TYPE
product: Windows
targetos: Windows
req.typenames: AUDIO_CURVE_TYPE
---

# AUDIO_CURVE_TYPE enumeration


## -description


The <b>AUDIO_CURVE_TYPE</b> enumeration defines constants that specify a curve algorithm to be applied to set a volume level. 


## -syntax


````
typedef enum _AUDIO_CURVE_TYPE { 
  AUDIO_CURVE_TYPE_NONE          = 0,
  AUDIO_CURVE_TYPE_WINDOWS_FADE  = 1
} AUDIO_CURVE_TYPE;
````


## -enum-fields




### -field AUDIO_CURVE_TYPE_NONE

Specifies that no curve algorithm will be applied.  When this curve is specified, the duration of the curve specified must be equal to 0.


### -field AUDIO_CURVE_TYPE_WINDOWS_FADE

Specifies that the algorithm that is applied to the volume setting must follow the curve shown in the diagram in the <b>Remarks</b> section.


## -remarks



The following snippet of pseudocode shows the logic for the algorithm that is applied to the volume setting to reach the target volume level.<pre class="syntax" xml:space="preserve"><code>// POWER IN AMPLITUDE: 1.75

// Fade In:
// Curve begins at 0 when nFrame = 0
// When nFrame gets to (nFrames - 1), curve = 1
//
// curve = pow(nFrame / (nFrames - 1), exponent)

float fFrameCount = nFrames - 1.0f;
for (UINT32 nFrame = 0; nFrame &lt; nFrames; nFrame++) {
    float curve = powf(nFrame / fFrameCount, 1.75f);
    for (UINT32 nChannel = 0; nChannel &lt; pWfx-&gt;nChannels; nChannel++) {            
            pFloat[nFrame * pWfx-&gt;nChannels + nChannel] *= curve;
    }
}

// Fade Out:
// curve begins at 1 when nFrame = 0
// When nFrame gets to (nFrames - 1), curve = 0
//
// curve = pow(1 - (nFrame / (nFrames - 1)), exponent)

float fFrameCount = nFrames - 1.0f;
for (UINT32 nFrame = 0; nFrame &lt; nFrames; nFrame++) {
    float curve = powf(1.0f - (nFrame / fFrameCount), 1.75f);
    for (UINT32 nChannel = 0; nChannel &lt; pWfx-&gt;nChannels; nChannel++) {            
            pFloat[nFrame * pWfx-&gt;nChannels + nChannel] *= curve;
    }
}
</code></pre>


And the following diagram shows a graphical representation of the preceding pseudocode for setting the volume level.

<img alt="Graphical representation of volume level curve" src="images/curve_type.png"/>




## -see-also

<a href="..\ksmedia\ns-ksmedia-_tagksaudioengine_volumelevel.md">KSAUDIOENGINE_VOLUMELEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh831855">KSPROPERTY_AUDIOENGINE_VOLUMELEVEL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20AUDIO_CURVE_TYPE enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

