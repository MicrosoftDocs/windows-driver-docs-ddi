---
UID: NF:portcls.IPreFetchOffset.SetPreFetchOffset
title: IPreFetchOffset::SetPreFetchOffset method
author: windows-driver-content
description: The SetPreFetchOffset method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.
old-location: audio\iprefetchoffset_setprefetchoffset.htm
old-project: audio
ms.assetid: fef8e8b8-7e79-4d88-b643-9b371e4297fd
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IPreFetchOffset, IPreFetchOffset interface [Audio Devices], SetPreFetchOffset method, IPreFetchOffset::SetPreFetchOffset, SetPreFetchOffset method [Audio Devices], SetPreFetchOffset method [Audio Devices], IPreFetchOffset interface, SetPreFetchOffset,IPreFetchOffset.SetPreFetchOffset, audio.iprefetchoffset_setprefetchoffset, audmp-routines_7fb7bb20-d9e0-4022-9de4-1c5952bfccf8.xml, portcls/IPreFetchOffset::SetPreFetchOffset
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IPreFetchOffset.SetPreFetchOffset
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPreFetchOffset::SetPreFetchOffset method


## -description


The <code>SetPreFetchOffset</code> method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.


## -syntax


````
VOID SetPreFetchOffset(
  [in] ULONG PreFetchOffset
);
````


## -parameters




### -param PreFetchOffset [in]

Specifies the prefetch offset size in bytes.


## -returns



None




## -remarks



A WavePci miniport driver calls the <code>SetPreFetchOffset</code> method to specify the prefetch offset of a hardware-accelerated DirectSound output stream.

The prefetch offset is the number of bytes of data separating the write cursor from the play cursor in the audio device's hardware buffer:

<ul>
<li>
The write cursor specifies the buffer position into which a DirectSound application can safely write the next sound sample.

</li>
<li>
The play cursor specifies the buffer position of the sound sample that is currently being played by the audio device.

</li>
</ul>
For more information about write cursors and play cursors, see <a href="..\ksmedia\ns-ksmedia-ksaudio_position.md">KSAUDIO_POSITION</a>.

For information about using <code>SetPreFetchOffset</code> to control a DirectSound stream's prefetch offset, see <a href="https://msdn.microsoft.com/92a0163f-29b1-4e15-88ab-67e1097d015e">Prefetch Offsets</a>.




## -see-also

<a href="..\ksmedia\ns-ksmedia-ksaudio_position.md">KSAUDIO_POSITION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>



<a href="..\portcls\nn-portcls-iprefetchoffset.md">IPreFetchOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536727">IMiniportWavePciStream::GetPosition</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPreFetchOffset::SetPreFetchOffset method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

