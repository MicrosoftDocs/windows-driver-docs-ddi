---
UID: NS:ntddndis._NDIS_OPER_STATE
title: _NDIS_OPER_STATE (ntddndis.h)
description: The NDIS_OPER_STATE structure provides the current operational state of an NDIS network interface.
old-location: netvista\ndis_oper_state.htm
tech.root: netvista
ms.assetid: c08f8bcd-23fc-445c-9c42-e5c4edc75d78
ms.date: 05/02/2018
keywords: ["_NDIS_OPER_STATE structure"]
ms.keywords: "*PNDIS_OPER_STATE, NDIS_OPER_STATE, NDIS_OPER_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_OPER_STATE, PNDIS_OPER_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_OPER_STATE, ndis_status_ref_d5bb44f8-a279-4806-b81b-87e109078a82.xml, netvista.ndis_oper_state, ntddndis/NDIS_OPER_STATE, ntddndis/PNDIS_OPER_STATE"
f1_keywords:
 - "ntddndis/NDIS_OPER_STATE"
req.header: ntddndis.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_OPER_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_OPER_STATE, *PNDIS_OPER_STATE
---

# _NDIS_OPER_STATE structure


## -description


The NDIS_OPER_STATE structure provides the current operational state of an NDIS network
  interface.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_OPER_STATE structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_OPER_STATE_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_OPER_STATE_REVISION_1.


### -field OperationalStatus

The 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_oper_status">NET_IF_OPER_STATUS</a> operational status
     type.


### -field OperationalStatusFlags

This member provides the reason why the 
     <b>OperationalStatus</b> member is set to <b>NET_IF_OPER_STATUS_DOWN</b> or NET_IF_OPER_STATUS_DORMANT. This
     member is a ULONG value that contains a bitwise OR of a combination of the following flags:
     





#### NET_IF_OPER_STATUS_DOWN_NOT_AUTHENTICATED

The operational status is set to <b>NET_IF_OPER_STATUS_DOWN</b> because the default port of the
       miniport adapter is not authenticated.



#### NET_IF_OPER_STATUS_DOWN_NOT_MEDIA_CONNECTED

The operational status is set to <b>NET_IF_OPER_STATUS_DOWN</b> because the miniport adapter is not in
       a media-connected state.



#### NET_IF_OPER_STATUS_DORMANT_PAUSED

The operational status is set to <b>NET_IF_OPER_STATUS_DORMANT</b> because the miniport adapter is in
       the paused or pausing state.



#### NET_IF_OPER_STATUS_DORMANT_LOW_POWER

The operational status is set to <b>NET_IF_OPER_STATUS_DORMANT</b> because the miniport adapter is in a
       low power state.


## -remarks



For the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-oper-status">NDIS_STATUS_OPER_STATUS</a> status
    indication, NDIS supplies an NDIS_OPER_STATE structure in the 
    <b>StatusBuffer</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a> structure.

NDIS_STATUS_OPER_STATUS indicates the current operational state of an NDIS network interface to
    overlying drivers.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-oper-status">NDIS_STATUS_OPER_STATUS</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_oper_status">NET_IF_OPER_STATUS</a>
 

 

