---
UID: NS:ndis._NDIS_PROTOCOL_RESTART_PARAMETERS
title: "_NDIS_PROTOCOL_RESTART_PARAMETERS"
author: windows-driver-content
description: The NDIS_PROTOCOL_RESTART_PARAMETERS structure defines restart parameters for a protocol driver when NDIS calls the ProtocolNetPnPEvent function to indicate a NetEventRestart event.
old-location: netvista\ndis_protocol_restart_parameters.htm
old-project: netvista
ms.assetid: 722287da-e0ee-41d5-b85a-0ec55eac41b9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_PROTOCOL_RESTART_PARAMETERS, NDIS_PROTOCOL_RESTART_PARAMETERS, NDIS_PROTOCOL_RESTART_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_RESTART_PARAMETERS, PNDIS_PROTOCOL_RESTART_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_RESTART_PARAMETERS, ndis/NDIS_PROTOCOL_RESTART_PARAMETERS, ndis/PNDIS_PROTOCOL_RESTART_PARAMETERS, netvista.ndis_protocol_restart_parameters, protocol_structures_ref_1a426da7-b2f9-49b0-9069-24ceddcd8ad1.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_PROTOCOL_RESTART_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_PROTOCOL_RESTART_PARAMETERS, *PNDIS_PROTOCOL_RESTART_PARAMETERS
---

# _NDIS_PROTOCOL_RESTART_PARAMETERS structure


## -description


The NDIS_PROTOCOL_RESTART_PARAMETERS structure defines restart parameters for a protocol driver when
  NDIS calls the 
  <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function to
  indicate a 
  <b>NetEventRestart</b> event.


## -syntax


````
typedef struct _NDIS_PROTOCOL_RESTART_PARAMETERS {
  NDIS_OBJECT_HEADER       Header;
  PUCHAR                   FilterModuleNameBuffer;
  ULONG                    FilterModuleNameBufferLength;
  PNDIS_RESTART_ATTRIBUTES RestartAttributes;
  NET_IFINDEX              BoundIfIndex;
  NET_LUID                 BoundIfNetluid;
  ULONG                    Flags;
} NDIS_PROTOCOL_RESTART_PARAMETERS, *PNDIS_PROTOCOL_RESTART_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PROTOCOL_RESTART_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_PROTOCOL_RESTART_PARAMETERS, the 
     <b>Revision</b> member to NDIS_PROTOCOL_RESTART_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PROTOCOL_RESTART_PARAMETERS_REVISION_1.


### -field FilterModuleNameBuffer

A list of the names of the underlying filter modules. For each name, the buffer contains a USHORT
     value followed by a wide character string. Use the first USHORT value in the buffer to determine the
     length of the first string. Use the length of the first string to determine the start of the next
     string. Continue in this manner until the number of bytes that are retrieved from the buffer equals the
     number of bytes that are specified in the 
     <b>FilterModuleNameBufferLength</b> member.


### -field FilterModuleNameBufferLength

The length, in bytes, of the buffer in the 
     <b>FilterModuleNameBuffer</b> member.


### -field RestartAttributes

A pointer to the first entry in a list of 
     <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a> structures.
     Use the 
     <b>Next</b> member of the NDIS_RESTART_ATTRIBUTES structure to get the next structure in the list.


### -field BoundIfIndex

The NDIS network interface index of the highest-level interface that is stacked on the miniport
     adapter. That is, if there are virtual miniports or filter modules that are installed over the miniport
     adapter, this member is the 
     <i>IfIndex</i> of the highest-level virtual miniport or filter module.


### -field BoundIfNetluid

The NDIS 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value (that is also the network interface
     name (<i>ifName</i> in 
     RFC 2863)) of the highest-level interface that is stacked on the miniport
     adapter. That is, if there are virtual miniports or filter modules that are installed over the miniport
     adapter, this member is the NET_LUID value of the highest-level virtual miniport or filter
     module.


### -field Flags

Reserved for future use.


## -remarks



NDIS passes an NDIS_PROTOCOL_RESTART_PARAMETERS structure to a protocol driver when it calls the 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function to
    indicate a 
    <b>NetEventRestart</b> event.

Each name that is specified in the buffer in the 
    <b>FilterModuleNameBuffer</b> member is not guaranteed to be NULL-terminated. The USHORT value at the
    start of each string contains the length, in bytes, of the string. Protocol drivers should check the
    value of the 
    <b>FilterModuleNameBufferLength</b> member before they access the buffer.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a>



<a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROTOCOL_RESTART_PARAMETERS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

