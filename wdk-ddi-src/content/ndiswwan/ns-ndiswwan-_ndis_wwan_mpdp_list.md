---
UID: NS:ndiswwan._NDIS_WWAN_MPDP_LIST
title: _NDIS_WWAN_MPDP_LIST
author: windows-driver-content
description: The NDIS_WWAN_MPDP_LIST structure contains a list of existing Multiple Packet Data Protocol (MPDP) interfaces for the mobile broadband device representing the primary PDP context/EPS bearer.
tech.root: netvista
ms.assetid: 42de1468-e1ef-4391-a454-c7978987ded1
ms.author: windowsdriverdev
ms.date: 06/25/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NDIS_WWAN_MPDP_LIST, NDIS_WWAN_MPDP_LIST, *PNDIS_WWAN_MPDP_LIST, 
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
req.typenames: NDIS_WWAN_MPDP_LIST, *PNDIS_WWAN_MPDP_LIST
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndiswwan.h
api_name: 
-	_NDIS_WWAN_MPDP_LIST
product:
- Windows
targetos: Windows
---

# _NDIS_WWAN_MPDP_LIST structure

## -description

The **NDIS_WWAN_MPDP_LIST** structure contains a list of existing Multiple Packet Data Protocol (MPDP) interfaces for the mobile broadband device representing the primary PDP context/EPS bearer.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_MPDP_LIST** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for *set* operations. Miniport drivers must set the header with the same values when they send the data structure to the MBB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_MPDP_LIST_REVISION_1 |
| Size | `sizeof(NDIS_WWAN_MPDP_LIST)` | 
 
### -field uStatus

A **WWAN_STATUS** value that indicates the result of the query request.
 
### -field ChildInterfaceList
 
If **uStatus** == WWAN_STATUS_SUCCESS, this field contains a list of the existing MPDP interfaces. The **ElementType** member of this list header must be **WwanStructMPDPChildInterface**, and the **ElementCount** member of interface GUIDs must follow this header.

## -remarks

This structure is used in an [NDIS_STATUS_WWAN_MPDP_LIST](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-wwan-mpdp-list) status indication, which is sent as an asynchronous response to an [OID_WWAN_MPDP](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-wwan-mpdp) query request.

## -see-also

[NDIS_STATUS_WWAN_MPDP_LIST](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-wwan-mpdp-list)

[OID_WWAN_MPDP](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-wwan-mpdp)
