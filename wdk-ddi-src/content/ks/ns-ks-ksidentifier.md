---
UID: NS:ks.KSIDENTIFIER
title: KSIDENTIFIER
author: windows-driver-content
description: The KSIDENTIFIER structure specifies a GUID that uniquely identifies a related set of GUIDs, and an index value to refer to a specific member within that set.
old-location: stream\ksidentifier.htm
old-project: stream
ms.assetid: b89977da-d3ac-4f1f-867e-b3b7912b955d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSDEGRADE, *PKSEVENT, *PKSIDENTIFIER, *PKSMETHOD, *PKSPIN_INTERFACE, *PKSPIN_MEDIUM, *PKSPROPERTY, KSDEGRADE, KSEVENT, KSIDENTIFIER, KSIDENTIFIER structure [Streaming Media Devices], KSMETHOD, KSPIN_INTERFACE, KSPIN_MEDIUM, KSPROPERTY, PKSIDENTIFIER, PKSIDENTIFIER structure pointer [Streaming Media Devices], ks-struct_652a0465-0c2b-4e46-ac43-7a6c5bbdaf80.xml, ks/KSIDENTIFIER, ks/PKSIDENTIFIER, stream.ksidentifier"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSIDENTIFIER
product:
- Windows
targetos: Windows
req.typenames: KSIDENTIFIER, *PKSIDENTIFIER
---

# KSIDENTIFIER structure


## -description


The KSIDENTIFIER structure specifies a GUID that uniquely identifies a related set of GUIDs, and an index value to refer to a specific member within that set.


## -struct-fields




### -field _IDENTIFIER

 


### -field _IDENTIFIER.Set

 


### -field _IDENTIFIER.Id

 


### -field _IDENTIFIER.Flags

 


### -field Set

Specifies a GUID that identifies a kernel streaming property, event, method, communication bus set. The KSPIN_INTERFACE structure describes a specific interface within an interface set. The KSDEGRADE structure contains specifics of degradation strategies. For more information see <b>Remarks</b>


### -field Id

Specifies the member of the property, event, method set. For KSPIN_MEDIUM, identifies a unique connection on the bus. For KSPIN_INTERFACE, specifies the ID number of this particular interface within the interface set. For KSDEGRADE, specifies the set-specific identifier for an item within the set.


### -field Flags

Specifies the request type. If you are writing a stream class minidriver, also see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565176">KSPROPERTY_ITEM</a> for class-specific flag information. <b>Flags</b> should be one of the values listed in the following table. Some of the flags may be combined using a bitwise OR operation.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_GET

</td>
<td>
Retrieves the value of the specified property item.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_SET

</td>
<td>
Sets the value of the specified property item.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_SETSUPPORT

</td>
<td>
Queries if the driver supports this property set.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_BASICSUPPORT

</td>
<td>
Queries the request types that the driver handles for this property item. Returns KSPROPERTY_TYPE_GET or KSPROPERTY_TYPE_SET or both. All property sets must support this flag.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_DEFAULTVALUES

</td>
<td>
Queries the default values for the specified property item. Returns a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff565966">KSPROPERTY_VALUES</a>.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_RELATIONS

</td>
<td>
Queries all properties with dependencies on the current setting of this property. Specifies that the property relations list is to be returned, or the amount of buffer room required by such a list if the return buffer is the size of a ULONG. Each element is on FILE_QUAD_ALIGNMENT, preceded by a KSMULTIPLE_ITEM structure. This is not valid when querying support of the property set in general. All property sets must support this flag.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_SERIALIZESET

</td>
<td>
Serialize the property set, using the standard KSPROPERTY_SERIALHDR and KSPROPERTY_SERIAL structures.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_UNSERIALIZESET

</td>
<td>
Unserialize the property set, using the standard KSPROPERTY_SERIALHDR and KSPROPERTY_SERIAL structures.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_SERIALIZESIZE

</td>
<td>
Returns a ULONG specifying size of the property data when serialized as part of a KSPROPERTY_TYPE_SERIALIZESET request. A size of zero indicates that a property does not need to be serialized.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_SERIALIZERAW

</td>
<td>
Specifies that the properties in this set should be serialized by the property set support handler, if one exists. If not, the call fails. The serialization format is private. This operation must be the inverse of KSPROPERTY_TYPE_UNSERIALIZERAW.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_TOPOLOGY

</td>
<td>
Property passed is of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566720">KSP_NODE</a>, where <b>NodeId</b> indicates the numeric ID of the topology node. Do not set this flag on its own; instead, OR it with other flags in this table.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_UNSERIALIZERAW

</td>
<td>
Specifies that the provided buffer contains a group of properties that belong to this set that should be unserialized by the property set support handler, if one exists. If not, the call fails. The serialization format is private. This operation must be the inverse of KSPROPERTY_TYPE_SERIALIZERAW. 

</td>
</tr>
</table>
 

Specifies the request type. This flag should be one of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSEVENT_TYPE_ENABLE

</td>
<td>
Enables event notification for this event type. The driver continues event notification until the client explicitly disables it.

</td>
</tr>
<tr>
<td>
KSEVENT_TYPE_ONESHOT

</td>
<td>
Enables event notification for the next occurrence of this event only. The client does not need to (and should not) disable the event once it has occurred.

</td>
</tr>
<tr>
<td>
KSEVENT_TYPE_SETSUPPORT

</td>
<td>
Queries for the list of event sets, or for support of a particular event set.

</td>
</tr>
<tr>
<td>
KSEVENT_TYPE_BASICSUPPORT

</td>
<td>
Queries for support of a particular event type.

</td>
</tr>
<tr>
<td>
KSEVENT_TYPE_ENABLEBUFFERED

</td>
<td>
Instead of notifying the client, the driver queues event notifications. The client then issues a second IOCTL_KS_ENABLE_EVENT request with the KSEVENT_TYPE_QUERYBUFFER to receive the queued event notifications.

</td>
</tr>
<tr>
<td>
KSEVENT_TYPE_TOPOLOGY

</td>
<td>
Indicates that the event passed is of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561937">KSE_NODE</a>, where <b>NodeId</b> indicates the numeric ID of the topology node. Do not set this flag on its own; instead, OR it with other flags from this list.

</td>
</tr>
<tr>
<td>
KSEVENT_TYPE_QUERYBUFFER

</td>
<td>
Retrieves the next buffered event notification.

</td>
</tr>
</table>
 

Specifies the request type. Also, see the KSMETHOD_TYPE_Xxx flags for <a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>. A request can contain a combination of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Type of method request</th>
</tr>
<tr>
<td>
KSMETHOD_TYPE_BASICSUPPORT

</td>
<td>
Indicates to query the minidriver to determine if it supports the specified method of the method set.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_SEND

</td>
<td>
Indicates that the minidriver should execute the specified method. The effect of the method on the given parameters must be known to the client, that is, whether the parameters are read from, written to, both, or neither. The minidriver uses the KSMETHOD_ITEM structure to specify the method's effect on the parameters.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_SETSUPPORT

</td>
<td>
Indicates to query the minidriver to determine if it supports the specified method set.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_TOPOLOGY

</td>
<td>
Indicates that the specified method is of type KSM_NODE, where the <b>NodeId</b> member is the identifier of the topology node. Do not set this flag on its own; instead, OR it with other flags from this list.

</td>
</tr>
</table>
 

For KSDEGRADE, specifies either the current percentage of degradation, expressed in parts per thousand (where a value of 1000 represents no degradation), or specifies the amount of time in native units as specified by the interface.


#### - Alignment

Not used.  A member of an unnamed union used to force proper alignment on the unnamed structure.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structures are aliases for the KSIDENTIFIER structure. As such, their definitions are identical. 

The use of an ID within the set allows one to perform a single large compare for a set identifier, then smaller quick compares (for example, by using a switch statement for identifiers within a set). For example, a <i>property set</i> is referred to by a unique GUID identifier, and properties within that set are referred to by the short ID.

<i>Method</i>, <i>Event</i>, <i>Interface</i>, and <i>medium sets</i> can be thought of as "classes" of sets.

The size of the output buffer passed determines what data is returned from a KSPROPERTY_TYPE_BASICSUPPORT request. If the output buffer is the size of a ULONG, only the access flags are returned. If the output buffer is the size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565132">KSPROPERTY_DESCRIPTION</a> structure, the structure is filled with the access flags, the inclusive size of the entire values information, the property value type information, and the number of member lists that correspond to the structure.

For a KSPROPERTY_TYPE_RELATIONS request, data returned also depends on the size of the output buffer. If the output buffer size is zero, the size required to return the related properties is returned in <b>BytesReturned</b> with a warning status of STATUS_BUFFER_OVERFLOW. If the buffer is the size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563441">KSMULTIPLE_ITEM</a> structure, both the byte size and count of relations is returned. Otherwise, the buffer is expected to be long enough to return the KSMULTIPLE_ITEM structure and all related property identifiers, which is returned as a list of <b>KSIDENTIFIER</b> structures.

KSPROPERTY_TYPE_SERIALIZESET and KSPROPERTY_TYPE_UNSERIALIZESET requests allow interaction with multiple properties with a single call from the client. If the kernel streaming handler is being used to process property requests, these are broken up into multiple calls by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564263">KsPropertyHandler</a> function. When using this handler, the property set definition controls which properties are to be serialized. 

For serialization requests, the <b>SerializedSize</b> member of the relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff565176">KSPROPERTY_ITEM</a> structure is checked for a nonzero value that indicates the size, in bytes, of the property. If the value of the SerializedSize member is 1, it is unknown and must be queried (all unknown properties begin with a KSMULTIPLE_ITEM structure that can be queried separately). To query for the total size a serialization would take, the client passes a zero length buffer in the call to <b>DeviceIoControl</b>. <b>BytesReturned</b> then returns the size, in bytes, that the buffer must be to serialize the set, and a warning status of STATUS_BUFFER_OVERFLOW. A buffer allocated that size can then be filled with the serialized data.

The format of the serialization buffer is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565614">KSPROPERTY_SERIALHDR</a>, followed by serialized properties. Each property that follows contains a header (<a href="https://msdn.microsoft.com/library/windows/hardware/ff565224">KSPROPERTY_SERIAL</a>), followed by the property data, with the start of each property on FILE_LONG_ALIGNMENT. Note that the serial header structure is defined to be on FILE_LONG_ALIGNMENT.

KSPROPERTY_TYPE_SERIALIZERAW and KSPROPERTY_TYPE_UNSERIALIZERAW are supported if a property item handler exists. The <b>KsPropertyHandler</b> function invokes the handler provided by the minidriver. The buffer size required for serialization can also be queried by passing a zero-length buffer to a serialize raw request. Because handlers are attached to property items rather than the property set, a specific item within the property set must be specified in the <b>Property</b> parameter. This handler may deal with multiple properties within the set.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>, and KSPROPERTY structures are aliases for the KSIDENTIFIER structure. As such, their definitions are identical.

Microsoft provides several system-defined property set GUIDs. Minidrivers specify one of these GUIDs in the <b>Set</b> member. Kernel streaming property sets typically begin with either a <i>KSPROPSETID</i> or a <i>PROPSETID</i> prefix. Kernel streaming property sets are defined in <i>ks.h</i>, <i>ksmedia.h</i>, <i>bdamedia.h</i>, and possibly other header files.

For more information about kernel streaming properties, see <a href="https://msdn.microsoft.com/933bbe81-92d8-4bcc-b935-9ae929464ca1">KS Properties, Events, and Methods</a>.

Microsoft provides several system-defined event set GUIDs. Minidrivers specify one of these GUIDs in the <b>Set</b> member. Kernel streaming event sets typically begin with a <i>KSEVENTSETID</i> prefix. Kernel streaming event sets are defined in <i>ks.h</i>, <i>ksmedia.h</i>, <i>bdamedia.h</i>, and possibly other header files.

For more information about kernel streaming events, see <a href="https://msdn.microsoft.com/933bbe81-92d8-4bcc-b935-9ae929464ca1">KS Properties, Events, and Methods</a>.

Microsoft provides several system-defined method set GUIDs. Minidrivers specify one of these GUIDs in the <b>Set</b> member. Kernel streaming method sets typically begin with a <i>KSMETHODSETID</i> prefix. Kernel streaming method sets are defined in <i>ks.h</i>, <i>ksmedia.h</i>, <i>bdamedia.h</i>, and possibly other header files.

For more information about kernel streaming methods, see <a href="https://msdn.microsoft.com/933bbe81-92d8-4bcc-b935-9ae929464ca1">KS Properties, Events, and Methods</a>.

A client can use the IOCTL_KS_METHOD request along with the KSMETHOD structure to execute methods on a kernel streaming object that the minidriver handles. For more information, see <a href="https://msdn.microsoft.com/1d7bd6f4-0aaf-4d77-8132-f551fd2ecbd2">KS Methods</a>.

The KSPIN_MEDIUM structure identifies a medium, with a unique medium GUID and instance identifier, which is generated in a bus-specific manner. There is a reserved identifier value KSMEDIUM_TYPE_ANYINSTANCE that is used when bus instances are not of concern. For example, the KSMEDIUMSETID_Standard refers to the system bus, of which there should only be one. So this instance identifier is always used just as a convenience.

A pin may support multiple mediums and interfaces on those mediums. The way in which a pin is described implies that the list of interfaces is supported on all mediums enumerated for a pin. If there is a case in which this is not true, another pin may be used to describe each subset of interfaces for the specific mediums.

The medium is also cached by kernel streaming to speed up the search for a possible connection.

An example of use of this structure can be found in a tuner sample, in which KSPIN_MEDIUM represents unique connections between tuners, crossbars, and other tuner components.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> and KSDEGRADE structures are aliases for the <b>KSIDENTIFIER</b> structure. As such, their definitions are identical.

The <b>Flags</b> member can contain different values based on the type of signal degradation that the client employs. See <a href="https://msdn.microsoft.com/359e6e12-903f-4037-8f35-b090ce41f770">Quality Management</a>. for more details on different strategies for solving QM problems by reducing signal quality.

Because <b>Flags</b> contains a ULONG value, multiple Skip requests may be needed to remedy the QM issue.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>
 

 

