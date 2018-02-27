---
UID: NF:portcls.IMiniportMidiStream.SetFormat
title: IMiniportMidiStream::SetFormat method
author: windows-driver-content
description: The SetFormat method sets the KS data format of the MIDI stream.
old-location: audio\iminiportmidistream_setformat.htm
old-project: audio
ms.assetid: 35e11004-c716-4c6a-ba0a-be04750afb7a
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IMiniportMidiStream, IMiniportMidiStream interface [Audio Devices], SetFormat method, IMiniportMidiStream::SetFormat, SetFormat method [Audio Devices], SetFormat method [Audio Devices], IMiniportMidiStream interface, SetFormat,IMiniportMidiStream.SetFormat, audio.iminiportmidistream_setformat, audmp-routines_9e75b920-4cc0-4acb-83e6-f970524e0587.xml, portcls/IMiniportMidiStream::SetFormat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IMiniportMidiStream.SetFormat
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportMidiStream::SetFormat method


## -description


The <code>SetFormat</code> method sets the KS data format of the MIDI stream.


## -syntax


````
NTSTATUS SetFormat(
  [in] PKSDATAFORMAT DataFormat
);
````


## -parameters




### -param DataFormat [in]

Specifies the new format for the stream. This parameter is a pointer to a structure of type <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>.


## -returns



<code>SetFormat</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>SetFormat</code> method essentially does nothing because the data format of a MIDI stream cannot be changed to anything other than MIDI. This method is provided for the sake of completeness and for orthogonality with the <code>SetFormat</code> methods in the <b>IMiniportWaveCyclic</b> and <b>IMiniportWavePci</b> interfaces. See the trivial implementation of this method in the fmsynth sample audio driver in the Microsoft Windows Driver Kit (WDK). You can use the sample code as a template for your own implementation. 




## -see-also

<a href="..\portcls\nn-portcls-iminiportmidistream.md">IMiniportMidiStream</a>



<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportMidiStream::SetFormat method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

