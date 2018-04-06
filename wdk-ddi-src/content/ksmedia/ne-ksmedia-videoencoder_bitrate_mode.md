---
UID: NE:ksmedia.VIDEOENCODER_BITRATE_MODE
title: VIDEOENCODER_BITRATE_MODE
author: windows-driver-content
description: The VIDEOENCODER_BITRATE_MODE enumeration describes the bit rate encoding modes supported by the device.
old-location: stream\videoencoder_bitrate_mode.htm
old-project: stream
ms.assetid: f941269b-65f3-4245-994f-0a4f6356cf88
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ConstantBitRate, VIDEOENCODER_BITRATE_MODE, VIDEOENCODER_BITRATE_MODE enumeration [Streaming Media Devices], VariableBitRateAverage, VariableBitRatePeak, encoderef_9d060a81-91a8-4e1a-9043-17cbb179b386.xml, ksmedia/ConstantBitRate, ksmedia/VIDEOENCODER_BITRATE_MODE, ksmedia/VariableBitRateAverage, ksmedia/VariableBitRatePeak, stream.videoencoder_bitrate_mode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	VIDEOENCODER_BITRATE_MODE
product:
- Windows
targetos: Windows
req.typenames: VIDEOENCODER_BITRATE_MODE
---

# VIDEOENCODER_BITRATE_MODE enumeration


## -description


The VIDEOENCODER_BITRATE_MODE enumeration describes the bit rate encoding modes supported by the device.


## -enum-fields




### -field ConstantBitRate


      Specifies that the encoding bit rate is constant. 



### -field VariableBitRateAverage

Specifies that the encoding bit rate is variable, with the specified bit rate used as a guaranteed average over a specified window. The default window size is considered to be 5 minutes. That is, this guarantees that the average bit rate over the window period (5 minutes) will not exceed that specified in <a href="https://msdn.microsoft.com/library/windows/hardware/ff559520">ENCAPIPARAM_BITRATE</a>. 



### -field VariableBitRatePeak

Specifies that the encoding bit rate is variable with the specified bit rate used as an average with a peak not to exceed the specified peak bit rate over a specified window. The default window size is considered to be 500ms (classically one GOP). That is, this bit rate is "constant quality" − the bit rate is expected to average around <a href="https://msdn.microsoft.com/library/windows/hardware/ff559520">ENCAPIPARAM_BITRATE</a> but may spike above this. It cannot exceed the bit rate specified in <a href="https://msdn.microsoft.com/library/windows/hardware/ff559529">ENCAPIPARAM_PEAK_BITRATE</a>.


## -remarks



For all three modes, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559520">ENCAPIPARAM_BITRATE</a> must be set to the expected average bit rate over a 5 minute period.

When <b>VariableBitRatePeak</b> mode is used, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559529">ENCAPIPARAM_PEAK_BITRATE</a> must also be set to the peak bit rate, which the VBR encoder must not exceed over a 500ms period (typically one GOP for MPEG-2 video).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559520">ENCAPIPARAM_BITRATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559524">ENCAPIPARAM_BITRATE_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559529">ENCAPIPARAM_PEAK_BITRATE</a>
 

 

