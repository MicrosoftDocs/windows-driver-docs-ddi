---
UID: NS:ndis._IPSEC_OFFLOAD_V2_UPDATE_SA
title: "_IPSEC_OFFLOAD_V2_UPDATE_SA"
author: windows-driver-content
description: The IPSEC_OFFLOAD_V2_UPDATE_SA structure updates information about security associations (SAs) that a miniport driver previously added to a NIC and a pointer to the next IPSEC_OFFLOAD_V2_UPDATE_SA structure in a linked list.
old-location: netvista\ipsec_offload_v2_update_sa.htm
old-project: netvista
ms.assetid: d9fe5fec-75e3-4ea6-a4ac-16756fa8dc38
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ipsec_offload_v2_update_sa, ndis/PIPSEC_OFFLOAD_V2_UPDATE_SA, IPSEC_OFFLOAD_V2_UPDATE_SA, PIPSEC_OFFLOAD_V2_UPDATE_SA structure pointer [Network Drivers Starting with Windows Vista], task_offload_IPsecv2_ref_2a34fbb7-fa5d-49f3-844c-c5e8df229a54.xml, _IPSEC_OFFLOAD_V2_UPDATE_SA, ndis/IPSEC_OFFLOAD_V2_UPDATE_SA, IPSEC_OFFLOAD_V2_UPDATE_SA structure [Network Drivers Starting with Windows Vista], *PIPSEC_OFFLOAD_V2_UPDATE_SA, PIPSEC_OFFLOAD_V2_UPDATE_SA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	IPSEC_OFFLOAD_V2_UPDATE_SA
product: Windows
targetos: Windows
req.typenames: IPSEC_OFFLOAD_V2_UPDATE_SA, *PIPSEC_OFFLOAD_V2_UPDATE_SA
---

# _IPSEC_OFFLOAD_V2_UPDATE_SA structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_UPDATE_SA structure updates information about security associations (SAs) that a
  miniport driver previously added to a NIC and a pointer to the next IPSEC_OFFLOAD_V2_UPDATE_SA structure in
  a linked list.


## -syntax


````
typedef struct _IPSEC_OFFLOAD_V2_UPDATE_SA {
  NDIS_OBJECT_HEADER         Header;
  NDIS_HANDLE                OffloadHandle;
  IPSEC_OFFLOAD_V2_OPERATION Operation;
  IPSEC_OFFLOAD_V2_SPI_TYPE  Spi;
  ULONG                      SequenceNumberHighOrder;
} IPSEC_OFFLOAD_V2_UPDATE_SA, *PIPSEC_OFFLOAD_V2_UPDATE_SA;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     IPSEC_OFFLOAD_V2_UPDATE_SA structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_IPSEC_OFFLOAD_V2_UPDATE_SA_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IPSEC_OFFLOAD_V2_UPDATE_SA_REVISION_1.


### -field OffloadHandle

An NDIS handle that identifies the SA. The miniport driver provided this handle in response to an 
     OID set request of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>.


### -field Operation

The IPsec operation for which the SA is to be used. The 
     <a href="..\ndis\ne-ndis-_ipsec_offload_v2_operation.md">
     IPSEC_OFFLOAD_V2_OPERATION</a> enumeration defines the supported operations.


### -field Spi

A 32 bit security parameters index (SPI) for the SA.


### -field SequenceNumberHighOrder

The high-order bit of an IPsec sequence number. This bit is not included in the IPsec
     header.


## -remarks



The IPSEC_OFFLOAD_V2_UPDATE_SA structure specifies updates for a SA and a pointer to the next
    IPSEC_OFFLOAD_V2_UPDATE_SA structure in a linked list. The IPSEC_OFFLOAD_V2_UPDATE_SA structure is used
    with the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-update-sa">
    OID_TCP_TASK_IPSEC_OFFLOAD_V2_UPDATE_SA</a> OID.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="..\ndis\ne-ndis-_ipsec_offload_v2_operation.md">IPSEC_OFFLOAD_V2_OPERATION</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-update-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_UPDATE_SA</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IPSEC_OFFLOAD_V2_UPDATE_SA structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

