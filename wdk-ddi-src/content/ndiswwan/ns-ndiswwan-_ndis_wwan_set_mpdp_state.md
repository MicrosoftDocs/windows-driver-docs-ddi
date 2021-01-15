---
UID: NS:ndiswwan._NDIS_WWAN_SET_MPDP_STATE
title: _NDIS_WWAN_SET_MPDP_STATE (ndiswwan.h)
description: The NDIS_WWAN_SET_MPDP_STATE structure contains information for performing an operation on a Multiple Packet Data Protocol (MPDP) interface.
tech.root: netvista
ms.date: 06/25/2018
keywords: ["NDIS_WWAN_SET_MPDP_STATE structure"]
ms.keywords: _NDIS_WWAN_SET_MPDP_STATE, NDIS_WWAN_SET_MPDP_STATE, *PNDIS_WWAN_SET_MPDP_STATE,
req.header: ndiswwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NDIS_WWAN_SET_MPDP_STATE, *PNDIS_WWAN_SET_MPDP_STATE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_WWAN_SET_MPDP_STATE
 - ndiswwan/_NDIS_WWAN_SET_MPDP_STATE
 - PNDIS_WWAN_SET_MPDP_STATE
 - ndiswwan/PNDIS_WWAN_SET_MPDP_STATE
 - NDIS_WWAN_SET_MPDP_STATE
 - ndiswwan/NDIS_WWAN_SET_MPDP_STATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_SET_MPDP_STATE
 - PNDIS_WWAN_SET_MPDP_STATE
 - NDIS_WWAN_SET_MPDP_STATE
---

# _NDIS_WWAN_SET_MPDP_STATE structure


## -description

The **NDIS_WWAN_SET_MPDP_STATE** structure contains information for performing an operation on a Multiple Packet Data Protocol (MPDP) interface.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_MPDP_STATE** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for *set* operations. Miniport drivers must set the header with the same values when they send the data structure to the MBB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SET_MPDP_STATE_REVISION_1 |
| Size | `sizeof(NDIS_WWAN_SET_MPDP_STATE)` | 

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field Info

 
A formatted [**NDIS_WWAN_MPDP_INFO**](ns-ndiswwan-_ndis_wwan_mpdp_info.md) structure that contains the information for the miniport driver to use in the MPDP interface operation.

## -remarks

This structure is used in an [OID_WWAN_MPDP](/windows-hardware/drivers/network/oid-wwan-mpdp) set request.

## -see-also

[**NDIS_WWAN_MPDP_INFO**](ns-ndiswwan-_ndis_wwan_mpdp_info.md)

[OID_WWAN_MPDP](/windows-hardware/drivers/network/oid-wwan-mpdp)

