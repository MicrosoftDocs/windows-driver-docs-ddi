---
UID: NS:portcls.PCPROPERTY_ITEM
title: PCPROPERTY_ITEM (portcls.h)
description: The PCPROPERTY_ITEM structure describes a property that is supported by a particular filter, pin, or node.
old-location: audio\pcproperty_item.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PCPROPERTY_ITEM structure"]
ms.keywords: "*PPCPROPERTY_ITEM, PCPROPERTY_ITEM, PCPROPERTY_ITEM structure [Audio Devices], PPCPROPERTY_ITEM, PPCPROPERTY_ITEM structure pointer [Audio Devices], audio.pcproperty_item, audpc-struct_6d95504b-3ecc-47dc-b98f-b6ebfa40d749.xml, portcls/PCPROPERTY_ITEM, portcls/PPCPROPERTY_ITEM"
req.header: portcls.h
req.include-header: Portcls.h
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
req.typenames: PCPROPERTY_ITEM, *PPCPROPERTY_ITEM
f1_keywords:
 - PPCPROPERTY_ITEM
 - portcls/PPCPROPERTY_ITEM
 - PCPROPERTY_ITEM
 - portcls/PCPROPERTY_ITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - portcls.h
api_name:
 - PPCPROPERTY_ITEM
 - PCPROPERTY_ITEM
---

# PCPROPERTY_ITEM structure


## -description

The <b>PCPROPERTY_ITEM</b> structure describes a property that is supported by a particular filter, pin, or node.

## -struct-fields

### -field Set

Specifies the property set. This member is a pointer to a GUID that uniquely identifies the property set. See the list of property-set GUIDs in <a href="/windows-hardware/drivers/audio/audio-drivers-property-sets">Audio Drivers Property Sets</a>.

### -field Id

Specifies the property ID. This member identifies a property item within the property set. If the property set contains N items, valid property IDs are integers in the range 0 to N-1.

### -field Flags

Specifies the types of property requests that the driver supports. Set this member to the bitwise OR of some or all of the flag bits that appear in the following table.

<table>
<tr>
<th>Flag bits</th>
<th>Type of property request</th>
</tr>
<tr>
<td>
PCPROPERTY_ITEM_FLAG_GET

</td>
<td>
Request to get the current property data setting.

</td>
</tr>
<tr>
<td>
PCPROPERTY_ITEM_FLAG_SET

</td>
<td>
Request to set the current property data setting.

</td>
</tr>
<tr>
<td>
PCPROPERTY_ITEM_FLAG_DEFAULTVALUES

</td>
<td>
Request for the driver's default values for the property data.

</td>
</tr>
<tr>
<td>
PCPROPERTY_ITEM_FLAG_BASICSUPPORT

</td>
<td>
Request for basic support, which specifies which request types the driver handles for this property, and also specifies the valid data type and the valid ranges for the property data.

</td>
</tr>
<tr>
<td>
PCPROPERTY_ITEM_FLAG_SERIALIZESIZE

</td>
<td>
Request for the size of the property data for this property when it is serialized as part of a KSPROPERTY_TYPE_SERIALIZESET request.

</td>
</tr>
<tr>
<td>
PCPROPERTY_ITEM_FLAG_SERIALIZERAW

</td>
<td>
Request to serialize this property in a driver-dependent manner. This operation is the inverse of PCPROPERTY_ITEM_FLAG_UNSERIALIZERAW.

</td>
</tr>
<tr>
<td>
PCPROPERTY_ITEM_FLAG_UNSERIALIZERAW

</td>
<td>
Request to unserialize this property in a driver-dependent manner. This operation is the inverse of PCPROPERTY_ITEM_FLAG_SERIALIZERAW.

</td>
</tr>
<tr>
<td>
PCPROPERTY_ITEM_FLAG_SERIALIZE

</td>
<td>
PCPROPERTY_ITEM_FLAG_SERIALIZERAW | PCPROPERTY_ITEM_FLAG_UNSERIALIZERAW | PCPROPERTY_ITEM_FLAG_SERIALIZESIZE

</td>
</tr>
</table>

### -field Handler

Pointer to the property-handler routine. This member is a function pointer of type PCPFNPROPERTY_HANDLER, which is defined as follows:


```
  typedef NTSTATUS (*PCPFNPROPERTY_HANDLER)
  (
      IN PPCPROPERTY_REQUEST  PropertyRequest
  );
```

See the following Remarks section.

## -remarks

The <b>PCPROPERTY_ITEM</b> structure specifies a particular property item in an automation table. The <a href="/windows-hardware/drivers/ddi/portcls/ns-portcls-pcautomation_table">PCAUTOMATION_TABLE</a> structure points to an array of <b>PCPROPERTY_ITEM</b> structures.

When calling the <b>Handler</b> routine, the caller passes in a single call parameter, which is a pointer to a <a href="/windows-hardware/drivers/ddi/portcls/ns-portcls-_pcproperty_request">PCPROPERTY_REQUEST</a> structure. This structure is allocated by the caller, and the caller frees it under either of the following conditions:

<ol>
<li>
If the <b>Handler</b> routine returns any status code other than STATUS_PENDING, the caller frees the structure. In this case, the miniport driver should not attempt to access the structure after the <b>Handler</b> routine returns.

</li>
<li>
The <b>Handler</b> routine can also return STATUS_PENDING, in which case the miniport driver is obliged to call <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pccompletependingpropertyrequest">PcCompletePendingPropertyRequest</a> at a later time to complete the pending property request. The <b>PcCompletePendingPropertyRequest</b> function frees the structure. After calling <b>PcCompletePendingPropertyRequest</b>, the miniport driver should not attempt to access the structure.

</li>
</ol>
If the miniport driver attempts to access the structure after it has been freed, this action is likely to cause a bug check or to corrupt another driver's memory.

For more information about serialization and raw serialization of a property set, see <a href="/windows-hardware/drivers/stream/ks-properties">KS Properties</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/ns-portcls-_pcproperty_request">PCPROPERTY_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pccompletependingpropertyrequest">PcCompletePendingPropertyRequest</a>

