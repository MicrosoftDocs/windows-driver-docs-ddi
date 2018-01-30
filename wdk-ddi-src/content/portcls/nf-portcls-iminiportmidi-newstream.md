---
UID: NF:portcls.IMiniportMidi.NewStream
title: IMiniportMidi::NewStream method
author: windows-driver-content
description: The NewStream method creates a new instance of a logical stream associated with a specified physical channel.
old-location: audio\iminiportmidi_newstream.htm
old-project: audio
ms.assetid: 6760c893-0574-4fb1-b714-d506ebbd0872
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NewStream method [Audio Devices], IMiniportMidi interface, audio.iminiportmidi_newstream, audmp-routines_4cc2fc38-bf0b-467e-83d4-678189d8fc0f.xml, IMiniportMidi, portcls/IMiniportMidi::NewStream, IMiniportMidi::NewStream, NewStream method [Audio Devices], NewStream, IMiniportMidi interface [Audio Devices], NewStream method
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
-	IMiniportMidi.NewStream
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportMidi::NewStream method


## -description


The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.


## -syntax


````
NTSTATUS NewStream(
  [out]          PMINIPORTMIDISTREAM *Stream,
  [in, optional] PUNKNOWN            OuterUnknown,
  [in]           POOL_TYPE           PoolType,
  [in]           ULONG               Pin,
  [in]           BOOLEAN             Capture,
  [in]           PKSDATAFORMAT       DataFormat,
  [out]          PSERVICEGROUP       *ServiceGroup
);
````


## -parameters




### -param Stream [out]

Output pointer for the new stream. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream object's <a href="..\portcls\nn-portcls-iminiportmidistream.md">IMiniportMidiStream</a> interface.


### -param OuterUnknown [in, optional]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the stream object. This parameter is optional. If aggregation is not required, the caller specifies this parameter as <b>NULL</b>.


### -param PoolType [in]

Specifies the type of memory pool from which the storage for the DMA-channel object should be allocated. This parameter is set to one of the <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> enumeration values.


### -param Pin [in]

Specifies the pin ID. This parameter identifies the pin that is to be opened. If the MIDI miniport object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method outputs a filter descriptor that specifies a total of <i>n</i> pin factories on the filter, then valid pin IDs are in the range 0 to <i>n</i>-1.


### -param Capture [in]

Specifies whether the channel is to be used for capture or for playback. If <b>TRUE</b>, it is a capture (input) channel. If <b>FALSE</b>, it is a playback (output) channel.


### -param DataFormat [in]

Pointer to a <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a> structure that specifies the data format to use for this stream instance.


### -param ServiceGroup [out]

Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> interface of the stream's service group object. This is the service group that is being registered for interrupt notification.


## -returns


<code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.



## -remarks


The <code>NewStream</code> method sets the initial state of the stream to KSSTATE_STOP.

The <i>Stream</i>, <i>OuterUnknown</i>, and <i>ServiceGroup</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.



## -see-also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>

<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>

<a href="..\portcls\nn-portcls-iminiportmidistream.md">IMiniportMidiStream</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>

<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>

<a href="..\portcls\nn-portcls-iminiportmidi.md">IMiniportMidi</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportMidi::NewStream method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

