---
UID: NS:ndis._NDIS_STATUS_INDICATION
title: "_NDIS_STATUS_INDICATION"
author: windows-driver-content
description: NDIS and underlying drivers use the NDIS_STATUS_INDICATION structure to provide status indications to overlying protocol drivers.
old-location: netvista\ndis_status_indication.htm
old-project: netvista
ms.assetid: bfab907d-a90d-46a0-bd51-6f2b418e3f39
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_STATUS_INDICATION, NDIS_STATUS_INDICATION, NDIS_STATUS_INDICATION structure [Network Drivers Starting with Windows Vista], PNDIS_STATUS_INDICATION, PNDIS_STATUS_INDICATION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_STATUS_INDICATION, ndis/NDIS_STATUS_INDICATION, ndis/PNDIS_STATUS_INDICATION, ndis_status_ref_6c475f32-573d-4e1b-ae74-bd9e9b8943db.xml, netvista.ndis_status_indication"
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
-	NDIS_STATUS_INDICATION
product: Windows
targetos: Windows
req.typenames: NDIS_STATUS_INDICATION, *PNDIS_STATUS_INDICATION
---

# _NDIS_STATUS_INDICATION structure


## -description


NDIS and underlying drivers use the NDIS_STATUS_INDICATION structure to provide status indications to
  overlying protocol drivers.


## -syntax


````
typedef struct _NDIS_STATUS_INDICATION {
  NDIS_OBJECT_HEADER Header;
  NDIS_HANDLE        SourceHandle;
  NDIS_PORT_NUMBER   PortNumber;
  NDIS_STATUS        StatusCode;
  ULONG              Flags;
  NDIS_HANDLE        DestinationHandle;
  PVOID              RequestId;
  PVOID              StatusBuffer;
  ULONG              StatusBufferSize;
  GUID               Guid;
  PVOID              NdisReserved[4];
} NDIS_STATUS_INDICATION, *PNDIS_STATUS_INDICATION;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_STATUS_INDICATION structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_STATUS_INDICATION, the 
     <b>Revision</b> member to NDIS_STATUS_INDICATION_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_STATUS_INDICATION_REVISION_1.


### -field SourceHandle

The source of the status indication. If the source is a miniport adapter, it should be the handle
     that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function. If
     the source is a filter module, it should be the handle that NDIS passed to the 
     <i>NdisFilterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -field PortNumber

The source port of the status indication. If the status indication is not specific to a port, set 
     <b>PortNumber</b> to zero.


### -field StatusCode

The status code, either provided by NDIS or propagated from the underlying drivers. The value is
     an NDIS_STATUS_<i>XXX</i> code. For more information about NDIS_STATUS_<i>XXX</i> codes, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff570879">Status Indications</a>.


### -field Flags

The type of information in the status buffer at 
     <b>StatusBuffer</b> . Miniport drivers set this member to zero. This member is reserved for NDIS.


### -field DestinationHandle

A handle that identifies the overlying driver that should receive the status indication. If <b>NULL</b>,
     NDIS indicates the status to each protocol driver that is bound to the miniport adapter. If non-<b>NULL</b>,
     NDIS indicates the status only to the driver that 
     <b>DestinationHandle</b> identifies. In this case the driver must also set the 
     <b>RequestId</b> member. For more information about OID requests, see the Remarks section.


### -field RequestId

The OID request that is associated with the status indication. If there is no OID request that is
     associated with the status indication, 
     <b>RequestId</b> is <b>NULL</b>. Miniport drivers must set the 
     <b>RequestId</b> member if the status indication is associated with an OID request that the miniport
     driver completed with a returned status of NDIS_STATUS_INDICATION_REQUIRED. In this case, the driver
     must also set the 
     <b>DestinationHandle</b> member.
     

For more information about OID requests, see the following Remarks section.


### -field StatusBuffer

A pointer to a buffer that contains medium-specific data that depends on the value at 
     <b>StatusCode</b> . 
     

For example, if 
     <b>StatusCode</b> is 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567391">NDIS_STATUS_LINK_STATE</a>, this
     parameter points to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_link_state.md">NDIS_LINK_STATE</a> structure and 
     <b>StatusBufferSize</b> is 
     sizeof(NDIS_LINK_STATE).

For some NDIS_STATUS_<i>XXX</i> values, this pointer is <b>NULL</b> and 
     <b>StatusBufferSize</b> is set to zero.


### -field StatusBufferSize

The length, in bytes, of the status information buffer at 
     <b>StatusBuffer</b> .


### -field Guid

A private GUID that NDIS uses to generate a WMI notification. For more information about private
     GUIDs, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569641">OID_GEN_SUPPORTED_GUIDS</a>.


### -field NdisReserved

Reserved for NDIS.


## -remarks



Miniport drivers indicate status by calling the 
    <a href="..\ndis\nf-ndis-ndismindicatestatusex.md">NdisMIndicateStatusEx</a> function.
    Filter drivers call the 
    <a href="..\ndis\nf-ndis-ndisfindicatestatus.md">NdisFIndicateStatus</a> function.

Some OID requests enable a miniport driver to provide an OID completion status with a status
    indication. In this case, the miniport driver returns NDIS_STATUS_INDICATION_REQUIRED for the completion
    status of the OID request. A miniport driver cannot return this status unless the particular OID allows
    it. To determine if this status is allowed, see the OID reference page.

If a status indication is associated with an OID request where the miniport driver returned
    NDIS_STATUS_INDICATION_REQUIRED, the driver that is making the status indication must set the 
    <b>DestinationHandle</b> and 
    <b>RequestId</b> members in the NDIS_STATUS_INDICATION structure.

In this case, the driver sets the 
    <b>DestinationHandle</b> and 
    <b>RequestId</b> members to the values from the 
    <b>RequestHandle</b> and 
    <b>RequestId</b> members in the 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure,
    respectively.

For example, in wireless networking, the processing of an OID request can take a very long time to
    complete. In this case, the miniport driver can complete the OID request immediately and provide a status
    indication later to provide the final result for the OID request.

Protocol drivers receive status indications at the 
    <a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a> function. Filter
    drivers receive status indications at the 
    <a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a> function.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567391">NDIS_STATUS_LINK_STATE</a>



<a href="..\ndis\nf-ndis-ndismindicatestatusex.md">NdisMIndicateStatusEx</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_link_state.md">NDIS_LINK_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558986">NDIS_TAPI_EVENT</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569641">OID_GEN_SUPPORTED_GUIDS</a>



<a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nf-ndis-ndisfindicatestatus.md">NdisFindicateStatus</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_STATUS_INDICATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

