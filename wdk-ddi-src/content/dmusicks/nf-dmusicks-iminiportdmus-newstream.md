---
UID: NF:dmusicks.IMiniportDMus.NewStream
title: IMiniportDMus::NewStream
author: windows-driver-content
description: The NewStream method creates a new instance of a logical stream associated with a specified physical channel.
old-location: audio\iminiportdmus_newstream.htm
old-project: audio
ms.assetid: aa221279-8d59-4f6f-8fc6-ad09e36a12a9
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportDMus interface [Audio Devices],NewStream method, IMiniportDMus.NewStream, IMiniportDMus::NewStream, NewStream, NewStream method [Audio Devices], NewStream method [Audio Devices],IMiniportDMus interface, audio.iminiportdmus_newstream, audmp-routines_a6630d1b-4a9d-4d4e-973a-09d541d7db70.xml, dmusicks/IMiniportDMus::NewStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	IMiniportDMus.NewStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportDMus::NewStream


## -description


The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.


## -parameters




### -param MXF [out]

Output pointer for the new stream. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536782">IMXF</a> interface.


### -param OuterUnknown [in, optional]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the stream object. This parameter is optional. If aggregation is not required, the caller specifies this parameter as <b>NULL</b>.


### -param PoolType [in]

Specifies the type of memory pool from which the storage for the DMA-channel object should be allocated. This parameter is set to one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a> enumeration values.


### -param PinID




### -param StreamType [in]

Specifies the type of data stream to create. This parameter is set to one of the following DMUS_STREAM_TYPE enumeration values:





#### DMUS_STREAM_MIDI_RENDER

Specifies a MIDI output (playback) stream.



#### DMUS_STREAM_MIDI_CAPTURE

Specifies a MIDI input stream.



#### DMUS_STREAM_WAVE_SINK

Specifies a wave output stream.

For more information, see the following Remarks section.


### -param DataFormat [in]

Pointer to a kernel streaming <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> structure specifying the data format to use for this instance


### -param ServiceGroup [out]

Output pointer for service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> interface of the stream's service group object. This is the service group that is being registered for interrupt notification.


### -param AllocatorMXF [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536491">IAllocatorMXF</a> object. This is the port driver's memory allocator, which is needed to recycle <a href="https://msdn.microsoft.com/library/windows/hardware/ff536340">DMUS_KERNEL_EVENT</a> structures.


### -param MasterClock [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536696">IMasterClock</a> object. This master clock passes a wrapper for the KS clock to the miniport driver. The master-clock pointer is required to sync to reference time.


### -param SchedulePreFetch [out]

Output pointer for the schedule-prefetch time. This parameter is a pointer to a caller-allocated ULONGLONG variable into which the method writes a time value that specifies how far ahead to query for events. The time is specified in 100-nanosecond units. The port driver is responsible for sequencing any events that exceed the amount of time that the miniport driver specifies here.


#### - PinId [in]

Specifies the pin ID. This parameter identifies the pin that is to be opened. If the DMus miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method outputs a filter descriptor that specifies a total of <i>n</i> pin factories on the filter, then valid pin IDs are in the range 0 to <i>n</i>-1.


## -returns



<code>NewStream</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



Note that the port driver creates the <b>IAllocatorMXF</b> object that the <code>NewStream</code> method inputs through the <i>pAllocatorMXF</i> parameter, but the miniport driver creates the <b>IMXF</b> object that the method outputs through the <i>ppMXF</i> parameter. For more information about <b>IMXF</b> and <b>IAllocatorMXF</b>, see <a href="https://msdn.microsoft.com/ce9ec589-0aea-4ed9-a60d-50f2ddfb0c13">MIDI Transport</a>.

The meaning of the <code>IMiniportDMus::NewStream</code> method's <i>StreamType</i> parameter is similar to that of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536710">IMiniportMidi::NewStream</a> method's <i>Capture</i> parameter:

<ul>
<li>
When creating a stream on a MIDI pin, the <b>IMiniportMidi::NewStream</b> method's <i>Capture</i> parameter indicates whether the pin is to serve as the sink for a MIDI render stream (<i>Capture</i> = <b>FALSE</b>) or as the source of a MIDI capture stream (<i>Capture</i> = <b>TRUE</b>).

</li>
<li>
Similarly, when creating a stream on a MIDI or DirectMusic pin, the <code>IMiniportDMus::NewStream</code> method's <i>StreamType</i> parameter can indicate whether the pin is to serve as the sink for a MIDI render stream (<i>StreamType</i> = DMUS_STREAM_MIDI_RENDER) or as the source of a MIDI capture stream (<i>StreamType</i> = DMUS_STREAM_MIDI_CAPTURE).

</li>
</ul>
However, a pin on a DirectMusic filter can support a third option that is not available with a MIDI filter. A pin can serve as the source of a wave output stream (<i>StreamType</i> = DMUS_STREAM_WAVE_SINK). The DMus port driver implements the wave sink for this stream. After creating the wave output stream, the DMus port driver queries the stream object (which the port driver obtains through the <code>IMiniportDMus::NewStream</code> method's <i>ppMXF</i> output parameter) for its <a href="https://msdn.microsoft.com/library/windows/hardware/ff537011">ISynthSinkDMus</a> interface. The port driver's wave sink calls the <b>Render</b> method on this interface to pull wave data from the software synthesizer. For more information, see <a href="https://msdn.microsoft.com/37ba9ad5-8b35-4252-a6fd-46dead924294">A Wave Sink for Kernel-Mode Software Synthesizers</a>.

The <i>ppMXF</i>, <i>pOuterUnknown</i>, <i>ppServiceGroup</i>, <i>pAllocatorMXF</i>, and <i>pMasterClock</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536340">DMUS_KERNEL_EVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536491">IAllocatorMXF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536782">IMXF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536696">IMasterClock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536699">IMiniportDMus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536710">IMiniportMidi::NewStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537011">ISynthSinkDMus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>
 

 

