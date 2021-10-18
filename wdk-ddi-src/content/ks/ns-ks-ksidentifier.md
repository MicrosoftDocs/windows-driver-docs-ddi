---
UID: NS:ks.__unnamed_struct_1
title: KSIDENTIFIER (ks.h)
description: The KSIDENTIFIER structure specifies a GUID that uniquely identifies a related set of GUIDs, and an index value to refer to a specific member within that set.
old-location: stream\ksidentifier.htm
tech.root: stream
ms.date: 07/15/2021
ms.custom: contperf-fy22q1
keywords: ["KSIDENTIFIER structure"]
ms.keywords: "*PKSDEGRADE, *PKSEVENT, *PKSIDENTIFIER, *PKSMETHOD, *PKSPIN_INTERFACE, *PKSPIN_MEDIUM, *PKSPROPERTY, KSDEGRADE, KSEVENT, KSIDENTIFIER, KSIDENTIFIER structure [Streaming Media Devices], KSMETHOD, KSPIN_INTERFACE, KSPIN_MEDIUM, KSPROPERTY, PKSIDENTIFIER, PKSIDENTIFIER structure pointer [Streaming Media Devices], ks-struct_652a0465-0c2b-4e46-ac43-7a6c5bbdaf80.xml, ks/KSIDENTIFIER, ks/PKSIDENTIFIER, stream.ksidentifier"
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
targetos: Windows
req.typenames: KSIDENTIFIER, *PKSIDENTIFIER
f1_keywords:
 - PKSIDENTIFIER
 - ks/PKSIDENTIFIER
 - KSIDENTIFIER
 - ks/KSIDENTIFIER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSIDENTIFIER
 - KSIDENTIFIER
---

# KSIDENTIFIER structure

## -description

The KSIDENTIFIER structure specifies a GUID that uniquely identifies a related set of GUIDs, and an index value to refer to a specific member within that set.

The [**KSDEGRADE**](/windows-hardware/drivers/stream/ksdegrade-structure), [**KSEVENT**](/windows-hardware/drivers/stream/ksevent-structure), [**KSMETHOD**](/windows-hardware/drivers/stream/ksmethod-structure), [**KSPIN_INTERFACE**](/windows-hardware/drivers/stream/kspin-interface-structure), [**KSPIN_MEDIUM**](/windows-hardware/drivers/stream/kspin-medium-structure), and [**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure) typedefs are aliases for the **KSIDENTIFIER** structure. As such, their definitions are identical. See the individual typedef topics for specifics on usage.

## -remarks

### Members

`Set`

Specifies a GUID that identifies a kernel streaming property, event, method, communication bus set. The **KSPIN_INTERFACE** structure describes a specific interface within an interface set. The **KSDEGRADE** structure contains specifics of degradation strategies. For more information, see the **Remarks** section below.

`Id`

Specifies the member of the property, event, method set. For **KSPIN_MEDIUM**, identifies a unique connection on the bus. For **KSPIN_INTERFACE**, specifies the ID number of this particular interface within the interface set. For **KSDEGRADE**, specifies the set-specific identifier for an item within the set.

`Flags`

Specifies the request type. If you are writing a stream class minidriver, also see [KSPROPERTY_ITEM](./ns-ks-ksproperty_item.md) for class-specific flag information. **Flags** should be one of the values listed in the following table. Some of the flags may be combined using a bitwise OR operation.

See the [**KSDEGRADE**](/windows-hardware/drivers/stream/ksdegrade-structure), [**KSEVENT**](/windows-hardware/drivers/stream/ksevent-structure), [**KSMETHOD**](/windows-hardware/drivers/stream/ksmethod-structure), [**KSPIN_INTERFACE**](/windows-hardware/drivers/stream/kspin-interface-structure), [**KSPIN_MEDIUM**](/windows-hardware/drivers/stream/kspin-medium-structure), and [**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure) typedef topics for specifics on usage.

Specifies the **KSPROPERTY** request type.

| KSPROPERTY Flag Value | Description |
|--|--|
| KSPROPERTY_TYPE_GET | Retrieves the value of the specified property item. |
| KSPROPERTY_TYPE_SET | Sets the value of the specified property item. |
| KSPROPERTY_TYPE_SETSUPPORT | Queries if the driver supports this property set. |
| KSPROPERTY_TYPE_BASICSUPPORT | Queries the request types that the driver handles for this property item. Returns KSPROPERTY_TYPE_GET or KSPROPERTY_TYPE_SET or both. All property sets must support this flag. |
| KSPROPERTY_TYPE_DEFAULTVALUES | Queries the default values for the specified property item. Returns a structure of type [KSPROPERTY_VALUES](./ns-ks-ksproperty_values.md). |
| KSPROPERTY_TYPE_RELATIONS | Queries all properties with dependencies on the current setting of this property. Specifies that the property relations list is to be returned, or the amount of buffer room required by such a list if the return buffer is the size of a ULONG. Each element is on FILE_QUAD_ALIGNMENT, preceded by a KSMULTIPLE_ITEM structure. This is not valid when querying support of the property set in general. All property sets must support this flag. |
| KSPROPERTY_TYPE_SERIALIZESET | Serialize the property set, using the standard KSPROPERTY_SERIALHDR and KSPROPERTY_SERIAL structures. |
| KSPROPERTY_TYPE_UNSERIALIZESET | Unserialize the property set, using the standard **KSPROPERTY_SERIALHDR** and **KSPROPERTY_SERIAL** structures. |
| KSPROPERTY_TYPE_SERIALIZESIZE | Returns a ULONG specifying size of the property data when serialized as part of a KSPROPERTY_TYPE_SERIALIZESET request. A size of zero indicates that a property does not need to be serialized. |
| KSPROPERTY_TYPE_SERIALIZERAW | Specifies that the properties in this set should be serialized by the property set support handler, if one exists. If not, the call fails. The serialization format is private. This operation must be the inverse of KSPROPERTY_TYPE_UNSERIALIZERAW. |
| KSPROPERTY_TYPE_TOPOLOGY | Property passed is of type [KSP_NODE](./ns-ks-ksp_node.md), where **NodeId** indicates the numeric ID of the topology node. Do not set this flag on its own; instead, OR it with other flags in this table. |
| KSPROPERTY_TYPE_UNSERIALIZERAW | Specifies that the provided buffer contains a group of properties that belong to this set that should be unserialized by the property set support handler, if one exists. If not, the call fails. The serialization format is private. This operation must be the inverse of KSPROPERTY_TYPE_SERIALIZERAW. |

Specifies the **KSEVENT** request type. This flag should be one of the values listed in the following table.

| KSEVENT Flag Value | Description |
|--|--|
| KSEVENT_TYPE_ENABLE | Enables event notification for this event type. The driver continues event notification until the client explicitly disables it. |
| KSEVENT_TYPE_ONESHOT | Enables event notification for the next occurrence of this event only. The client does not need to (and should not) disable the event once it has occurred. |
| KSEVENT_TYPE_SETSUPPORT | Queries for the list of event sets, or for support of a particular event set. |
| KSEVENT_TYPE_BASICSUPPORT | Queries for support of a particular event type. |
| KSEVENT_TYPE_ENABLEBUFFERED | Instead of notifying the client, the driver queues event notifications. The client then issues a second IOCTL_KS_ENABLE_EVENT request with the KSEVENT_TYPE_QUERYBUFFER to receive the queued event notifications. |
| KSEVENT_TYPE_TOPOLOGY | Indicates that the event passed is of type [KSE_NODE](./ns-ks-kse_node.md), where **NodeId** indicates the numeric ID of the topology node. Do not set this flag on its own; instead, OR it with other flags from this list. |
| KSEVENT_TYPE_QUERYBUFFER | Retrieves the next buffered event notification. |

Specifies the **KSMETHOD** request type. Also, see the KSMETHOD_TYPE_Xxx flags for [KSMETHOD_ITEM](./ns-ks-ksmethod_item.md). A request can contain a combination of the values listed in the following table.

| KSMETHOD Flag Value | Description |
|--|--|
| KSMETHOD_TYPE_BASICSUPPORT | Indicates to query the minidriver to determine if it supports the specified method of the method set. |
| KSMETHOD_TYPE_SEND | Indicates that the minidriver should execute the specified method. The effect of the method on the given parameters must be known to the client, that is, whether the parameters are read from, written to, both, or neither. The minidriver uses the KSMETHOD_ITEM structure to specify the method's effect on the parameters. |
| KSMETHOD_TYPE_SETSUPPORT | Indicates to query the minidriver to determine if it supports the specified method set. |
| KSMETHOD_TYPE_TOPOLOGY | Indicates that the specified method is of type KSM_NODE, where the **NodeId** member is the identifier of the topology node. Do not set this flag on its own; instead, OR it with other flags from this list. |

For KSDEGRADE, specifies either the current percentage of degradation, expressed in parts per thousand (where a value of 1000 represents no degradation), or specifies the amount of time in native units as specified by the interface.

`Alignment`

Not used.  A member of an unnamed union used to force proper alignment on the unnamed structure.

### Notes

See the [**KSDEGRADE**](/windows-hardware/drivers/stream/ksdegrade-structure), [**KSEVENT**](/windows-hardware/drivers/stream/ksevent-structure), [**KSMETHOD**](/windows-hardware/drivers/stream/ksmethod-structure), [**KSPIN_INTERFACE**](/windows-hardware/drivers/stream/kspin-interface-structure), [**KSPIN_MEDIUM**](/windows-hardware/drivers/stream/kspin-medium-structure), and [**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure) typedef topics for specifics on usage.

The use of an ID within the set allows one to perform a single large compare for a set identifier, then smaller quick compares (for example, by using a switch statement for identifiers within a set). For example, a *property set* is referred to by a unique GUID identifier, and properties within that set are referred to by the short ID.

*Method*, *Event*, *Interface*, and *medium sets* can be thought of as "classes" of sets.

The size of the output buffer passed determines what data is returned from a KSPROPERTY_TYPE_BASICSUPPORT request. If the output buffer is the size of a ULONG, only the access flags are returned. If the output buffer is the size of the [KSPROPERTY_DESCRIPTION](./ns-ks-ksproperty_description.md) structure, the structure is filled with the access flags, the inclusive size of the entire values information, the property value type information, and the number of member lists that correspond to the structure.

For a KSPROPERTY_TYPE_RELATIONS request, data returned also depends on the size of the output buffer. If the output buffer size is zero, the size required to return the related properties is returned in **BytesReturned** with a warning status of STATUS_BUFFER_OVERFLOW. If the buffer is the size of a [KSMULTIPLE_ITEM](./ns-ks-ksmultiple_item.md) structure, both the byte size and count of relations is returned. Otherwise, the buffer is expected to be long enough to return the KSMULTIPLE_ITEM structure and all related property identifiers, which is returned as a list of **KSIDENTIFIER** structures.

KSPROPERTY_TYPE_SERIALIZESET and KSPROPERTY_TYPE_UNSERIALIZESET requests allow interaction with multiple properties with a single call from the client. If the kernel streaming handler is being used to process property requests, these are broken up into multiple calls by the [KsPropertyHandler](./nf-ks-kspropertyhandler.md) function. When using this handler, the property set definition controls which properties are to be serialized.

For serialization requests, the **SerializedSize** member of the relevant [KSPROPERTY_ITEM](./ns-ks-ksproperty_item.md) structure is checked for a nonzero value that indicates the size, in bytes, of the property. If the value of the SerializedSize member is 1, it is unknown and must be queried (all unknown properties begin with a KSMULTIPLE_ITEM structure that can be queried separately). To query for the total size a serialization would take, the client passes a zero length buffer in the call to **DeviceIoControl**. **BytesReturned** then returns the size, in bytes, that the buffer must be to serialize the set, and a warning status of STATUS_BUFFER_OVERFLOW. A buffer allocated that size can then be filled with the serialized data.

The format of the serialization buffer is a [KSPROPERTY_SERIALHDR](./ns-ks-ksproperty_serialhdr.md), followed by serialized properties. Each property that follows contains a header ([KSPROPERTY_SERIAL](./ns-ks-ksproperty_serial.md)), followed by the property data, with the start of each property on FILE_LONG_ALIGNMENT. Note that the serial header structure is defined to be on FILE_LONG_ALIGNMENT.

KSPROPERTY_TYPE_SERIALIZERAW and KSPROPERTY_TYPE_UNSERIALIZERAW are supported if a property item handler exists. The **KsPropertyHandler** function invokes the handler provided by the minidriver. The buffer size required for serialization can also be queried by passing a zero-length buffer to a serialize raw request. Because handlers are attached to property items rather than the property set, a specific item within the property set must be specified in the **Property** parameter. This handler may deal with multiple properties within the set.

Microsoft provides several system-defined property set GUIDs. Minidrivers specify one of these GUIDs in the **Set** member. Kernel streaming property sets typically begin with either a *KSPROPSETID* or a *PROPSETID* prefix. Kernel streaming property sets are defined in *ks.h*, *ksmedia.h*, *bdamedia.h*, and possibly other header files.

For more information about kernel streaming properties, see [KS Properties, Events, and Methods](/windows-hardware/drivers/stream/ks-properties--events--and-methods).

Microsoft provides several system-defined event set GUIDs. Minidrivers specify one of these GUIDs in the **Set** member. Kernel streaming event sets typically begin with a *KSEVENTSETID* prefix. Kernel streaming event sets are defined in *ks.h*, *ksmedia.h*, *bdamedia.h*, and possibly other header files.

For more information about kernel streaming events, see [KS Properties, Events, and Methods](/windows-hardware/drivers/stream/ks-properties--events--and-methods).

Microsoft provides several system-defined method set GUIDs. Minidrivers specify one of these GUIDs in the **Set** member. Kernel streaming method sets typically begin with a *KSMETHODSETID* prefix. Kernel streaming method sets are defined in *ks.h*, *ksmedia.h*, *bdamedia.h*, and possibly other header files.

For more information about kernel streaming methods, see [KS Properties, Events, and Methods](/windows-hardware/drivers/stream/ks-properties--events--and-methods).

A client can use the IOCTL_KS_METHOD request along with the KSMETHOD structure to execute methods on a kernel streaming object that the minidriver handles. For more information, see [KS Methods](/windows-hardware/drivers/stream/ks-methods).

The **KSPIN_MEDIUM** structure identifies a medium, with a unique medium GUID and instance identifier, which is generated in a bus-specific manner. There is a reserved identifier value KSMEDIUM_TYPE_ANYINSTANCE that is used when bus instances are not of concern. For example, the KSMEDIUMSETID_Standard refers to the system bus, of which there should only be one. So this instance identifier is always used just as a convenience.

A pin may support multiple mediums and interfaces on those mediums. The way in which a pin is described implies that the list of interfaces is supported on all mediums enumerated for a pin. If there is a case in which this is not true, another pin may be used to describe each subset of interfaces for the specific mediums.

The medium is also cached by kernel streaming to speed up the search for a possible connection.

An example of use of this structure can be found in a tuner sample, in which **KSPIN_MEDIUM** represents unique connections between tuners, crossbars, and other tuner components.

The **Flags** member can contain different values based on the type of signal degradation that the client employs. See [Quality Management](/windows-hardware/drivers/stream/quality-management). for more details on different strategies for solving quality management problems by reducing signal quality.

Because **Flags** contains a ULONG value, multiple Skip requests may be needed to remedy the quality management issue.

## -see-also

[**KSDEGRADE**](/windows-hardware/drivers/stream/ksdegrade-structure)

[**KSEVENT**](/windows-hardware/drivers/stream/ksevent-structure)

[**KSMETHOD**](/windows-hardware/drivers/stream/ksmethod-structure)

[**KSPIN_INTERFACE**](/windows-hardware/drivers/stream/kspin-interface-structure)

[**KSPIN_MEDIUM**](/windows-hardware/drivers/stream/kspin-medium-structure)

[**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure)