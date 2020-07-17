---
UID: NS:ndiswwan._NDIS_WWAN_MPDP_STATE
title: _NDIS_WWAN_MPDP_STATE (ndiswwan.h)
description: The NDIS_WWAN_MPDP_STATE structure represents the state of a Multiple Packet Data Protocol (MPDP) interface after a requested operation.
tech.root: netvista
ms.assetid: 58bc3af3-8f33-41e3-9417-190da9be2b6c
ms.date: 06/25/2018
keywords: ["_NDIS_WWAN_MPDP_STATE structure"]
f1_keywords:
 - "ndiswwan/_NDIS_WWAN_MPDP_STATE"
 - "_NDIS_WWAN_MPDP_STATE"
ms.keywords: _NDIS_WWAN_MPDP_STATE, NDIS_WWAN_MPDP_STATE, *PNDIS_WWAN_MPDP_STATE, 
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
req.typenames: NDIS_WWAN_MPDP_STATE, *PNDIS_WWAN_MPDP_STATE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_MPDP_STATE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _NDIS_WWAN_MPDP_STATE structure

## -description

The **NDIS_WWAN_MPDP_STATE** structure represents the state of a Multiple Packet Data Protocol (MPDP) interface after a requested operation.

## -struct-fields

### -field Header
 
The header with type, revision, and size information about the **NDIS_WWAN_MPDP_STATE** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for *set* operations. Miniport drivers must set the header with the same values when they send the data structure to the MBB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_MPDP_STATE_REVISION_1 |
| Size | `sizeof(NDIS_WWAN_MPDP_STATE)` | 

### -field uStatus

A **WWAN_STATUS** value that indicates the result of the requested MPDP interface operation.
 
### -field Info
 
A formatted [**NDIS_WWAN_MPDP_INFO**](ns-ndiswwan-_ndis_wwan_mpdp_info.md) structure that contains information about the requested MPDP operation.

## -remarks

This structure is used in an [NDIS_STATUS_WWAN_MPDP_STATE](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-mpdp-state) status indication, which is sent as an asynchronous response to an [OID_WWAN_MPDP](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-mpdp) set request.

## -see-also

[**NDIS_WWAN_MPDP_INFO**](ns-ndiswwan-_ndis_wwan_mpdp_info.md)

[NDIS_STATUS_WWAN_MPDP_STATE](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-mpdp-state)

[OID_WWAN_MPDP](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-mpdp)
