---
UID: NE:ndiswwan._WWAN_MPDP_OPERATION
title: _WWAN_MPDP_OPERATION
author: windows-driver-content
description: The WWAN_MPDP_OPERATION enumeration describes the operation for a mobile broadband miniport driver to perform for a multiple Packet Data Protocol (MPDP) interface.
ms.assetid: b8436268-3236-4c86-9aa6-f8b6ae65c121
ms.author: windowsdriverdev
ms.date: 06/25/2018
ms.topic: enum
ms.keywords: _WWAN_MPDP_OPERATION, WWAN_MPDP_OPERATION, *PWWAN_MPDP_OPERATION, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ndiswwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_MPDP_OPERATION, *PWWAN_MPDP_OPERATION
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndiswwan.h
api_name: 
-	_WWAN_MPDP_OPERATION
product: Windows
targetos: Windows
---

# _WWAN_MPDP_OPERATION enumeration

## -description

The **WWAN_MPDP_OPERATION** enumeration describes an operation to perform on a multiple Packet Data Protocol (MPDP) interface/NetAdapter object.

## -enum-fields

### -field WwanMPDPOperationCreateChildInterface 

Create a new MPDP child interface.

### -field WwanMPDPOperationDeleteChildInterface 

Delete an existing MPDP child interface.

### -field WwanMPDPOperationMax 

The maximum value for this enumeration.

## -remarks

This enumeration is a member of the [**NDIS_WWAN_MPDP_INFO**](ns-ndiswwan-_ndis_wwan_mpdp_info.md) structure.

## -see-also

[**NDIS_WWAN_MPDP_INFO**](ns-ndiswwan-_ndis_wwan_mpdp_info.md)

[**NDIS_WWAN_SET_MPDP_STATE**](ns-ndiswwan-_ndis_wwan_set_mpdp_state.md)

[**NDIS_WWAN_MPDP_STATE**](ns-ndiswwan-_ndis_wwan_mpdp_state.md)

[OID_WWAN_MPDP](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-wwan-mpdp)