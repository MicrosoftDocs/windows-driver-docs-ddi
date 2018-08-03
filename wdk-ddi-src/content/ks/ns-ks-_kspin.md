---
UID: NS:ks._KSPIN
title: "_KSPIN"
author: windows-driver-content
description: The KSPIN structure describes an instantiated pin.
old-location: stream\kspin.htm
tech.root: stream
ms.assetid: 0d290872-0944-4599-9deb-9a4f7b2df0e5
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPIN, KSPIN, KSPIN structure [Streaming Media Devices], PKSPIN, PKSPIN structure pointer [Streaming Media Devices], _KSPIN, avstruct_9453feff-ba40-4f54-bdb6-07f4f31548aa.xml, ks/KSPIN, ks/PKSPIN, stream.kspin"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	ks.h
api_name:
-	KSPIN
product:
- Windows
targetos: Windows
req.typenames: KSPIN, *PKSPIN
---

# _KSPIN structure


## -description


The KSPIN structure describes an instantiated pin.


## -struct-fields




### -field Descriptor

A pointer to the pin descriptor for this particular pin. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a> for more information.


### -field Bag

This member specifies the KSOBJECT_BAG (the KSOBJECT_BAG structure is equivalent to type PVOID) for this particular pin instance. <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a> are structures used to associate dynamic memory with a specific AVStream object. Anything in the pin object bag is automatically cleaned up when the pin is closed.


### -field Context

A pointer to a buffer. Clients can use <b>Context</b> to associate context information with a specific pin instance. Typically, this is used for pin/stream extensions and is allocated in the create dispatch provided in the pin dispatch table. Note that any dynamic memory allocated for context information should be placed in the pin instance's object bag using <a href="https://msdn.microsoft.com/library/windows/hardware/ff560941">KsAddItemToObjectBag</a>. <b>Context</b> is initialized to the value of the <b>Context</b> member of the parent <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> at the time the pin is created. See <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.


### -field Id

This member specifies the pin type identifier. This is the index into the array of pin descriptors provided for the given filter type.


### -field Communication

This member specifies KSPIN_COMMUNICATION_NONE, KSPIN_COMMUNICATION_SINK, KSPIN_COMMUNICATION_SOURCE, KSPIN_COMMUNICATION_BOTH or KSPIN_COMMUNICATION_BRIDGE. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565194">KSPROPERTY_PIN_COMMUNICATION</a> for the meaning of each value. 


### -field ConnectionIsExternal

This member specifies a Boolean value that, if <b>TRUE</b>, indicates that the connected pin does not support the AVStream connection handshake. If <b>FALSE</b>, indicates that the connected pin supports the AVStream connection handshake. This is an indication of whether the connection between this pin and the pin it is connected to is a connection between two AVStream pins.


### -field ConnectionInterface

This member contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a> structure that identifies the interface being used for the connection. This information is supplied by the graph builder when the pin is created.


### -field ConnectionMedium

This member contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a> structure that identifies the connection medium this pin should use. This information is supplied by the graph builder when the pin is created.


### -field ConnectionPriority

This member contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564250">KSPRIORITY</a> structure that specifies the priority of the connection. This information is supplied by the graph builder when the pin is created.


### -field ConnectionFormat

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> structure that specifies the data format of the connection. This information is initially supplied by the graph builder when the pin is created and may be changed through property access or by format change messages inserted into the stream. Access to this member is synchronized by the filter control mutex. This member should not be changed by the client.


### -field AttributeList

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563441">KSMULTIPLE_ITEM</a> structure that specifies the list of attributes, supplied during pin creation, to describe the connection. Specifies the direction of data flow for this pin (KSPIN_DATAFLOW_IN or KSPIN_DATAFLOW_OUT). This information is a static attribute of the pin and appears in the pin descriptor. It is cached here for access at IRQL above PASSIVE_LEVEL.


### -field StreamHeaderSize

This member indicates the size in bytes of each <a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a> structure for this pin. Typically used for output pins, a client can set this to any value greater than <b>sizeof</b><i> (KSSTREAM_HEADER)</i> and have extended stream headers allocated (each stream header will be <b>StreamHeaderSize</b> bytes long). If a client does not set this member, this indicates that no extended information follows stream headers. In such a situation, each stream header is precisely <b>sizeof</b><i> (KSSTREAM_HEADER)</i>. Clients can set this in the pin creation dispatch.


### -field DataFlow

This member specifies the direction of data flow for the pin.  Possible settings are <b>KSPIN_DATAFLOW_IN</b>  and KSPIN_DATAFLOW_OUT.  This information is a static attribute of the pin and appears in relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff563533">KSPIN_DESCRIPTOR</a> structure. It is cached here for access at IRQL above PASSIVE_LEVEL.


### -field DeviceState

This member contains an enumeration of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a> that identifies the state to which the pin has been told to transition. Not necessarily the same as the state of the pipe, which is reported through <a href="https://msdn.microsoft.com/library/windows/hardware/ff556359">AVStrMiniPinSetDeviceState</a>. Initially KSSTATE_STOP, this member is changed when AVStream receives a connection state property set IOCTL. Access is synchronized using the <a href="https://msdn.microsoft.com/402795a0-e567-4e7e-a7d8-b2ce29ffb8fd">filter control mutex</a>. Minidrivers should not change this member. See note in Remarks section below. Also see the <i>ClientState</i> member.


### -field ResetState

This member contains an enumeration of type KSRESET that identifies the current reset state of the pin. Possible settings are KSRESET_BEGIN and KSRESET_END. This member is initially set to KSRESET_END and is changed through property access. Access to this member is synchronized by the <a href="https://msdn.microsoft.com/402795a0-e567-4e7e-a7d8-b2ce29ffb8fd">filter control mutex</a>. The client should not change this member.


### -field ClientState

This member specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a> at which the pin is currently set. Updated immediately before <a href="https://msdn.microsoft.com/library/windows/hardware/ff556359">AVStrMiniPinSetDeviceState</a> is called. If this callback routine fails, AVStream rolls back <i>ClientState</i> to its previous value. Minidrivers that fail state transitions and that check this member during processing should be aware of this sequence of events.


## -remarks



In many ways, pins are the focus of filter behavior. This is reflected in the fact that the pin structure has a large number of members. Many minidrivers need to refine pin behavior and maintain additional pin-associated context. For filters with fairly conventional pin behavior, no additional refinement or context is required. In many cases, default pin behavior is sufficient; the pins are accessed using <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.

For synchronization purposes, the lifetime of this object is the interval starting when the minidriver's PreCreate dispatch function is called and ending when the minidriver's Close dispatch function returns, assuming the function does not return STATUS_PENDING. If it does return STATUS_PENDING, the object's lifetime ends when the client indicates completion of the close request by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff561025">KsCompletePendingRequest</a>.

If the minidriver needs to determine whether it has been told to go to a specific <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a>, comparing the value of the <b>DeviceState</b> member of KSPIN to that state is not a reliable method. Instead, either look at the <i>ClientState</i> member, or create a variable in the <b>SetDeviceState</b> callback and then check this variable. <b>SetDeviceState</b> is a member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>.

Also see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563533">KSPIN_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560941">KsAddItemToObjectBag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561025">KsCompletePendingRequest</a>
 

 

