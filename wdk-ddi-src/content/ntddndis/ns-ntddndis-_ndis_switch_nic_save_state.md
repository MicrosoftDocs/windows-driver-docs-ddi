---
UID: NS:ntddndis._NDIS_SWITCH_NIC_SAVE_STATE
title: "_NDIS_SWITCH_NIC_SAVE_STATE"
author: windows-driver-content
description: The NDIS_SWITCH_NIC_SAVE_STATE structure specifies the run-time state information for a Hyper-V extensible switch port. The extensible switch extension uses this structure to save or restore run-time port information.
old-location: netvista\ndis_switch_nic_save_state.htm
old-project: netvista
ms.assetid: FBC2EE79-9D36-4CA9-A7BC-9C422DE51B13
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_SWITCH_NIC_SAVE_STATE, ,, A, C, D, E, H, I, N, NDIS_SWITCH_NIC_SAVE_STATE, NDIS_SWITCH_NIC_SAVE_STATE structure [Network Drivers Starting with Windows Vista], P, PNDIS_SWITCH_NIC_SAVE_STATE, PNDIS_SWITCH_NIC_SAVE_STATE structure pointer [Network Drivers Starting with Windows Vista], S, T, V, W, _, _NDIS_SWITCH_NIC_SAVE_STATE, netvista.ndis_switch_nic_save_state, ntddndis/NDIS_SWITCH_NIC_SAVE_STATE, ntddndis/PNDIS_SWITCH_NIC_SAVE_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	NDIS_SWITCH_NIC_SAVE_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_NIC_SAVE_STATE, *PNDIS_SWITCH_NIC_SAVE_STATE
---

# _NDIS_SWITCH_NIC_SAVE_STATE structure


## -description



The <b>NDIS_SWITCH_NIC_SAVE_STATE</b> structure specifies the run-time state information for a Hyper-V extensible switch port.  The extensible switch extension uses this structure to save or restore run-time port information.




## -syntax


````
typedef struct _NDIS_SWITCH_NIC_SAVE_STATE {
  NDIS_OBJECT_HEADER                 Header;
  ULONG                              Flags;
  NDIS_SWITCH_NIC_INDEX              NicIndex;
  NDIS_SWITCH_PORT_ID                PortId;
  GUID                               ExtensionId;
  NDIS_SWITCH_EXTENSION_FRIENDLYNAME ExtensionFriendlyName;
  GUID                               FeatureClassId;
  USHORT                             SaveDataSize;
  USHORT                             SaveDataOffset;
} NDIS_SWITCH_NIC_SAVE_STATE, *PNDIS_SWITCH_NIC_SAVE_STATE;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_NIC_SAVE_STATE</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_NIC_SAVE_STATE</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_NIC_SAVE_STATE_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_NIC_SAVE_STATE_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field PortId

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port.


### -field NicIndex

An NDIS_SWITCH_NIC_INDEX  value that contains the Nic Index for the network adapter. This value will always be 0. For more information, see <a href="https://msdn.microsoft.com/969333DA-0282-474B-8D56-72CD623C5329">Network Adapter Index Values</a>.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598268">OID_SWITCH_NIC_SAVE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598269">OID_SWITCH_NIC_SAVE_COMPLETE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598267">OID_SWITCH_NIC_RESTORE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh846215">OID_SWITCH_NIC_RESTORE_COMPLETE</a>


</li>
</ul>
<div class="alert"><b>Note</b>  The NDIS_SWITCH_EXTENSION_FRIENDLYNAME data type is type-defined by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451419">IF_COUNTED_STRING</a> structure. A string that is defined by this structure does not have to be null-terminated. However, the length of the string must be set in the <b>Length</b> member of this structure. If the string is null-terminated, the <b>Length</b> member must not include the terminating null character. 

</div>
<div> </div>
For more information on how to save or restore run-time port information, see <a href="https://msdn.microsoft.com/08A353F5-D8CB-4645-9337-8169D302F6F2">Managing Hyper-V Extensible Switch Run-Time Data</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598269">OID_SWITCH_NIC_SAVE_COMPLETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598267">OID_SWITCH_NIC_RESTORE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598268">OID_SWITCH_NIC_SAVE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451419">IF_COUNTED_STRING</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_NIC_SAVE_STATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

