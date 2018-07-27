---
UID: NS:dmusicks._DMUS_KERNEL_EVENT
title: "_DMUS_KERNEL_EVENT"
author: windows-driver-content
description: The DMUS_KERNEL_EVENT structure is used to package time-stamped music events.
old-location: audio\dmus_kernel_event.htm
tech.root: audio
ms.assetid: 652f64e2-310b-46c9-8b00-c827a7475b07
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: "*PDMUS_KERNEL_EVENT, DMUS_KERNEL_EVENT, DMUS_KERNEL_EVENT structure [Audio Devices], PDMUS_KERNEL_EVENT, PDMUS_KERNEL_EVENT structure pointer [Audio Devices], _DMUS_KERNEL_EVENT, aud-prop_b0db54b3-fff3-46f2-abd7-beb4fe189f8f.xml, audio.dmus_kernel_event, dmusicks/DMUS_KERNEL_EVENT, dmusicks/PDMUS_KERNEL_EVENT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dmusicks.h
req.include-header: Dmusicks.h
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
-	dmusicks.h
api_name:
-	DMUS_KERNEL_EVENT
product:
- Windows
targetos: Windows
req.typenames: DMUS_KERNEL_EVENT, *PDMUS_KERNEL_EVENT
---

# _DMUS_KERNEL_EVENT structure


## -description


The DMUS_KERNEL_EVENT structure is used to package time-stamped music events.


## -struct-fields




### -field bReserved


      Miniport drivers should not modify this member. Reserved for future use. Do not use.


### -field cbStruct


      Miniport drivers should not modify this member.
       This member specifies the size of the DMUS_KERNEL_EVENT structure itself and could change in the future.


### -field cbEvent

Specifies the unrounded number of event bytes referred to by <b>uData</b>.


### -field usChannelGroup

Specifies which channel group (set of 16 MIDI channels) receives or originated this event. This is unique only within the target MIDI device (miniport driver).


### -field usFlags

Specifies whether an event is a package and whether this event concludes the message. A package encapsulates a list of events that should be dealt with atomically. This member is a bitfield that can be set to the bitwise OR of one or more of the following flag bits:





#### DMUS_KEF_EVENT_COMPLETE (zero)

Specifies messages in which the entire message is contained either in <b>uData.abData</b> or in the buffer pointed to by <b>uData.pbData</b>. The former includes all short messages, and potentially includes very brief SysEx messages (see Microsoft Windows SDK documentation) as well. Keep in mind that <b>sizeof</b>(PBYTE) can be 8 instead of 4 on 64-bit versions of Windows.



#### DMUS_KEF_EVENT_INCOMPLETE

Specifies that this event is an incomplete package or SysEx message (see Windows SDK documentation). This flag specifies that the message continues beyond this event. During MIDI capture, the miniport driver can send "uncooked" MIDI events (raw MIDI input data) to the capture sink by specifying this flag.



#### DMUS_KEF_PACKAGE_EVENT

Specifies that this event is a package. The <b>uData.pPackageEvt</b> field contains a pointer to a chain of events which should be dealt with atomically.


### -field ullPresTime100ns

Specifies the presentation time for this event. This 64-bit value is expressed in 100-nanosecond units. The master clock should be used to evaluate this presentation time.


### -field ullBytePosition

8 16


### -field pNextEvt

Pointer to the next event in the list, or <b>NULL</b> if no event follows. This facilitates passing chains of identically time-stamped messages to the miniport driver. Additionally, hardware that does its own mixing can receive or transmit groups of messages at one time.


### -field uData


### -field uData.abData

A byte array containing <b>cbEvent</b> bytes of event data. The event data are typically MIDI status and data bytes. This member of <b>uData</b> is used if <b>cbEvent</b> is less than or equal to <b>sizeof</b>(PBYTE).


### -field uData.pbData

Pointer to a buffer containing <b>cbEvent</b> bytes of event data. The event data are typically MIDI status and data bytes. This member of <b>uData</b> is used if <b>uFlags</b> is set to DMUS_KEF_EVENT_COMPLETE and <b>cbEvent</b> is greater than <b>sizeof</b>(PBYTE).


### -field uData.pPackageEvt

Pointer to a chain of events, which is in the form of a linked list of DMUS_KERNEL_EVENT structures. The event data typically consist of MIDI status and data bytes. The events in the list are to be handled together. This member of <b>uData</b> is used if <b>uFlags</b> is set to DMUS_KEF_PACKAGE_EVENT.


## -remarks



The DMUS_KERNEL_EVENT structure is used by WDM audio drivers that provide kernel streaming support for DirectMusic.

While capturing a MIDI stream, the DMus port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536494">IAllocatorMXF::GetMessage</a> method to retrieve DMUS_KERNEL_EVENT structures to hold the captured data. While rendering a MIDI stream, the port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a> method to discard DMUS_KERNEL_EVENT structures as it finishes reading them. For more information, see <a href="https://msdn.microsoft.com/ce9ec589-0aea-4ed9-a60d-50f2ddfb0c13">MIDI Transport</a>.

In the case of MIDI capture, the DMUS_KERNEL_EVENT structure can be packaged with single, multiple, or fragmentary MIDI messages. The <b>usFlags</b> member should be set to DMUS_KEF_EVENT_INCOMPLETE unless it is a single complete MIDI message. This structure also contains:

<ul>
<li>
A time stamp relative to the master clock (ullPresTime100Ns)

</li>
<li>
Extended channel information (usChannelGroup)

</li>
</ul>
Mapping to the correct DLS instrument is implicit in the triplet of

&lt;<i>pin</i>, <i>channel_group</i>, <i>channel</i>&gt;

Presentation time does not advance during the states KSSTATE_PAUSE and KSSTATE_STOP, and is reset during KSSTATE_STOP. For more information, see <a href="https://msdn.microsoft.com/e3ffc7ca-f3cd-4989-af40-78b6a2438f95">KS Clocks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536494">IAllocatorMXF::GetMessage</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a>
 

 

