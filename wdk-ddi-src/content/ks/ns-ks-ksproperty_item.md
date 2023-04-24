---
UID: NS:ks.KSPROPERTY_ITEM
title: KSPROPERTY_ITEM (ks.h)
description: Drivers use the KSPROPERTY_ITEM structure to describe how they support a property in a property set.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KSPROPERTY_ITEM structure"]
ms.keywords: "*PKSPROPERTY_ITEM, KSPROPERTY_ITEM, KSPROPERTY_ITEM structure [Streaming Media Devices], PKSPROPERTY_ITEM, PKSPROPERTY_ITEM structure pointer [Streaming Media Devices], ks-struct_ae02482e-27d1-4485-8fe2-3b9a7393c683.xml, ks/KSPROPERTY_ITEM, ks/PKSPROPERTY_ITEM, stream.ksproperty_item"
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
req.typenames: KSPROPERTY_ITEM, *PKSPROPERTY_ITEM
f1_keywords:
 - PKSPROPERTY_ITEM
 - ks/PKSPROPERTY_ITEM
 - KSPROPERTY_ITEM
 - ks/KSPROPERTY_ITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSPROPERTY_ITEM
 - KSPROPERTY_ITEM
---

## -description

Drivers use the KSPROPERTY_ITEM structure to describe how they support a property in a property set.

## -struct-fields

### -field PropertyId

Specifies the ID of the property being described.

### -field GetPropertyHandler

Pointer to a minidriver-supplied [KStrGetPropertyHandler](/previous-versions/ff567177(v=vs.85)). If **NULL**, the property cannot be read. This member is used only by drivers that use the AVStream or Stream class interfaces.

### -field GetSupported

Set to **TRUE** if this property supports get requests, **FALSE** if it does not. (The class driver fulfills the request through the SRB_GET_DEVICE_PROPERTY or SRB_GET_STREAM_PROPERTY requests.) This member is used only by minidrivers running under stream class.

### -field MinProperty

Specifies the minimum buffer length to hold the property identifier. This must be at least **sizeof**([**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure)).

### -field MinData

Specifies the minimum buffer length to hold the data read from or written to this property.

### -field SetPropertyHandler

Pointer to a minidriver-supplied [KStrSetPropertyHandler](/previous-versions/ff567200(v=vs.85)). If **NULL**, the property cannot be set. This member is used only by drivers that use the AVStream or Stream class interfaces.

### -field SetSupported

Set to **TRUE** if this property supports set requests, **FALSE** if it does not. (The class driver fulfills the request through the SRB_SET_DEVICE_PROPERTY or SRB_SET_STREAM_PROPERTY requests.)

### -field Values

Pointer to a structure of type [**KSPROPERTY_VALUES**](./ns-ks-ksproperty_values.md). Specifies the acceptable and/or default values for the property. These are the same as the values reported by a driver in response to an IOCTL_KS_PROPERTY request with the KSPROPERTY_TYPE_BASICSUPPORT and KSPROPERTY_TYPE_DEFAULTVALUES flags set.

### -field RelationsCount

Specifies the number of entries in the array pointed to by the **Relations** member.

### -field Relations

Points to an array of [**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure) structures representing properties related to this one. Two properties are considered related if changing one property may affect the value of the other property. The **Flags** member of each entry is unused.

### -field SupportHandler

Provide this member only if implementing your own format for raw serialization or raw unserialization. Basic support queries, range queries, and relations queries are automatically handled by AVStream, which returns the relevant values from other members of this KSPROPERTY_ITEM structure.

### -field SerializedSize

Specifies the size of the property when serialized in a KSPROPERTY_TYPE_SERIALIZESET request. This should be zero if the property cannot be serialized. See [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) for more information.

## -remarks

Stream class minidrivers use KSPROPERTY_ITEM to describe to the client how to fulfill property requests on each property within a set. Handling for the property set as a whole is specified in the [KSPROPERTY_SET](./ns-ks-ksproperty_set.md) structure, which contains pointers to arrays of KSPROPERTY_ITEM structures.

The stream class driver handles property requests on behalf of the minidriver. When the stream class driver requires more information from the minidriver, it passes an SRB_XXX request to one of the minidriver's **StrMiniReceiveXXXRequest** routines. The stream class driver handles the different request types as listed in the following table.

| Property request flags value | Response |
|---|---|
| KSPROPERTY_TYPE_GET | If **GetSupported** is **TRUE**, the stream class driver submits an [**SRB_GET_DEVICE_PROPERTY**](/windows-hardware/drivers/stream/srb-get-device-property) or [**SRB_GET_STREAM_PROPERTY**](/windows-hardware/drivers/stream/srb-get-stream-property) request to the appropriate minidriver **StrMiniReceiveXXXRequest** routine. |
| KSPROPERTY_TYPE_SET | If **SetSupported** is **TRUE**, the stream class driver submits an [**SRB_SET_DEVICE_PROPERTY**](/windows-hardware/drivers/stream/srb-set-device-property) or [**SRB_SET_STREAM_PROPERTY**](/windows-hardware/drivers/stream/srb-set-stream-property) request to the appropriate minidriver **StrMiniReceiveXXXRequest** routine. |
| KSPROPERTY_TYPE_BASICSUPPORT | The stream class driver uses KSPROPERTY_ITEM to obtain the information necessary to fulfill this request. For example, to specify the data type and permitted ranges of the property data, they each use the **Values** member of this structure. |
| KSPROPERTY_TYPE_SETSUPPORT | The stream class driver completes the property request IRP as STATUS_SUCCESS only if the driver supplies an entry for the property set within its [**KSPROPERTY_SET**](./ns-ks-ksproperty_set.md) structure. |
| KSPROPERTY_TYPE_DEFAULTVALUES | The stream class driver uses the **Values** member of this structure to determine the default values for the property data. |
| KSPROPERTY_TYPE_RELATIONS | The stream class driver uses the **Relations** member to determine what properties are related to this property. |

If the client specifies KSPROPERTY_TYPE_DEFAULTVALUES, the driver uses the data buffer to return a description of its value type, including possibly its allowed range and default value. This flag is similar in result to KSPROPERTY_TYPE_BASICSUPPORT, except that any values returned are those that have been marked with KSPROPERTY_MEMBER_FLAG_DEFAULT in the **Flags** member of the structure [**KSPROPERTY_MEMBERSHEADER**](./ns-ks-ksproperty_membersheader.md).

For more information, see [KS Properties](/windows-hardware/drivers/stream/ks-properties).

## -see-also

[**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure)

[**KSPROPERTY_SET**](./ns-ks-ksproperty_set.md)

[**KSPROPERTY_VALUES**](./ns-ks-ksproperty_values.md)

[**SRB_GET_DEVICE_PROPERTY**](/windows-hardware/drivers/stream/srb-get-device-property)

[**SRB_GET_STREAM_PROPERTY**](/windows-hardware/drivers/stream/srb-get-stream-property)

[**SRB_SET_DEVICE_PROPERTY**](/windows-hardware/drivers/stream/srb-set-device-property)

[**SRB_SET_STREAM_PROPERTY**](/windows-hardware/drivers/stream/srb-set-stream-property)