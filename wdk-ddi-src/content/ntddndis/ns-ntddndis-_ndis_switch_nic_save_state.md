---
UID: NS:ntddndis._NDIS_SWITCH_NIC_SAVE_STATE
title: _NDIS_SWITCH_NIC_SAVE_STATE (ntddndis.h)
description: The NDIS_SWITCH_NIC_SAVE_STATE structure specifies the run-time state information for a Hyper-V extensible switch port. The extensible switch extension uses this structure to save or restore run-time port information.
old-location: netvista\ndis_switch_nic_save_state.htm
tech.root: netvista
ms.assetid: FBC2EE79-9D36-4CA9-A7BC-9C422DE51B13
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_NIC_SAVE_STATE structure"]
ms.keywords: "*PNDIS_SWITCH_NIC_SAVE_STATE, NDIS_SWITCH_NIC_SAVE_STATE, NDIS_SWITCH_NIC_SAVE_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_NIC_SAVE_STATE, PNDIS_SWITCH_NIC_SAVE_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_NIC_SAVE_STATE, netvista.ndis_switch_nic_save_state, ntddndis/NDIS_SWITCH_NIC_SAVE_STATE, ntddndis/PNDIS_SWITCH_NIC_SAVE_STATE"
req.header: ntddndis.h
req.include-header: Ndis.h, Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.typenames: NDIS_SWITCH_NIC_SAVE_STATE, *PNDIS_SWITCH_NIC_SAVE_STATE
f1_keywords:
 - _NDIS_SWITCH_NIC_SAVE_STATE
 - ntddndis/_NDIS_SWITCH_NIC_SAVE_STATE
 - PNDIS_SWITCH_NIC_SAVE_STATE
 - ntddndis/PNDIS_SWITCH_NIC_SAVE_STATE
 - NDIS_SWITCH_NIC_SAVE_STATE
 - ntddndis/NDIS_SWITCH_NIC_SAVE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_SWITCH_NIC_SAVE_STATE
---

# _NDIS_SWITCH_NIC_SAVE_STATE structure


## -description

The <b>NDIS_SWITCH_NIC_SAVE_STATE</b> structure specifies the run-time state information for a Hyper-V extensible switch port.  The extensible switch extension uses this structure to save or restore run-time port information.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_NIC_SAVE_STATE</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_NIC_SAVE_STATE</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_NIC_SAVE_STATE_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_NIC_SAVE_STATE_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field PortId

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port.

### -field NicIndex

An NDIS_SWITCH_NIC_INDEX  value that contains the Nic Index for the network adapter. This value will always be 0. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-adapter-index-values">Network Adapter Index Values</a>.

### -field ExtensionId

A GUID value that identifies the extensible switch extension.

### -field ExtensionFriendlyName

 An NDIS_SWITCH_EXTENSION_FRIENDLYNAME value that specifies the user-friendly description of the extensible switch extension.

### -field FeatureClassId

A GUID value that contains the identifier of the feature class related to the saved data. A feature class identifier is defined by the extension to uniquely identify components of its run-time data.

<div class="alert"><b>Note</b>  This member is optional. The extensible switch extension must set this member to 0 if the saved data has no feature class.</div>
<div> </div>

### -field SaveDataSize

A USHORT value that specified the size, in bytes, of the data that is contained in the <b>SaveData</b> member.

<div class="alert"><b>Note</b>  This value must be less than or equal to NDIS_SWITCH_NIC_SAVE_STATE_MAX_DATA_SIZE.</div>
<div> </div>

### -field SaveDataOffset

A USHORT value that contains the offset from the start of the structure to the run-time state information being saved or restored.

### -field SaveDataSizeOverflow

## -remarks

The <b>NDIS_SWITCH_NIC_SAVE_STATE</b> structure is used in the following OID requests: 

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-save">OID_SWITCH_NIC_SAVE</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-save-complete">OID_SWITCH_NIC_SAVE_COMPLETE</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-restore">OID_SWITCH_NIC_RESTORE</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-restore-complete">OID_SWITCH_NIC_RESTORE_COMPLETE</a>


</li>
</ul>
<div class="alert"><b>Note</b>  The NDIS_SWITCH_EXTENSION_FRIENDLYNAME data type is type-defined by the <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-if_counted_string_lh">IF_COUNTED_STRING</a> structure. A string that is defined by this structure does not have to be null-terminated. However, the length of the string must be set in the <b>Length</b> member of this structure. If the string is null-terminated, the <b>Length</b> member must not include the terminating null character. 

</div>
<div> </div>
For more information on how to save or restore run-time port information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-hyper-v-extensible-switch-run-time-data">Managing Hyper-V Extensible Switch Run-Time Data</a>.

## -see-also

<b></b>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-if_counted_string_lh">IF_COUNTED_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-restore">OID_SWITCH_NIC_RESTORE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-save">OID_SWITCH_NIC_SAVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-save-complete">OID_SWITCH_NIC_SAVE_COMPLETE</a>

