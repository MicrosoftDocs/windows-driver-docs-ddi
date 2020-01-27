---
UID: NS:ndiswwan._NDIS_WWAN_MPDP_INFO
title: _NDIS_WWAN_MPDP_INFO (ndiswwan.h)
description: The NDIS_WWAN_MPDP_INFO structure contains information for an operation to perform on a Multiple Packet Data Protocol (MPDP) interface.
tech.root: netvista
ms.assetid: d55a038d-2f2e-45f4-b306-afe5703c5357
ms.date: 06/25/2018
f1_keywords:
 - "ndiswwan/_NDIS_WWAN_MPDP_INFO"
ms.keywords: _NDIS_WWAN_MPDP_INFO, NDIS_WWAN_MPDP_INFO, *PNDIS_WWAN_MPDP_INFO, 
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
req.typenames: NDIS_WWAN_MPDP_INFO, *PNDIS_WWAN_MPDP_INFO
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_MPDP_INFO
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _NDIS_WWAN_MPDP_INFO structure

## -description

The **NDIS_WWAN_MPDP_INFO** structure contains information for an operation to perform on a Multiple Packet Data Protocol (MPDP) interface.

## -struct-fields

### -field Operation

An [**NDIS_WWAN_MPDP_OPERATION**](ne-ndiswwan-_wwan_mpdp_operation.md) value that specifies the operation to perform.
 
### -field ChildInterfaceGUID

The GUID of the child interface to be deleted, if **Operation** is set to **WwanMPDPOperationDeleteChildInterface**. If **Operation** is set to **WwanMPDPOperationCreateChildInterface**, then this value is the GUID of the newly created child interface.
 
### -field MacAddr
 
Currently unused.

## -remarks

This structure is a member of both the [**NDIS_WWAN_SET_MPDP_STATE**](ns-ndiswwan-_ndis_wwan_set_mpdp_state.md) structure and the [**NDIS_WWAN_MPDP_STATE**](ns-ndiswwan-_ndis_wwan_mpdp_state.md) structure.

## -see-also

[**NDIS_WWAN_MPDP_OPERATION**](ne-ndiswwan-_wwan_mpdp_operation.md)

[**NDIS_WWAN_SET_MPDP_STATE**](ns-ndiswwan-_ndis_wwan_set_mpdp_state.md)

[**NDIS_WWAN_MPDP_STATE**](ns-ndiswwan-_ndis_wwan_mpdp_state.md)

[OID_WWAN_MPDP](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-mpdp)
