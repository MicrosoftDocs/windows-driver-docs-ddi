---
UID: NS:wwan._WWAN_SLOT_INFO
title: _WWAN_SLOT_INFO (wwan.h)
description: The WWAN_SLOT_INFO structure represents the status of a specific SIM card slot on the modem.
old-location: netvista\wwan_slot_info_status.htm
tech.root: netvista
ms.assetid: F45D253E-E7D7-4600-AF8C-6D4EB096030D
ms.date: 05/02/2018
keywords: ["_WWAN_SLOT_INFO structure"]
ms.keywords: "*PWWAN_SLOT_INFO, PWWAN_SLOT_INFO, PWWAN_SLOT_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_SLOT_INFO, WWAN_SLOT_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_SLOT_INFO, netvista.wwan_slot_info_status, wwan/PWWAN_SLOT_INFO, wwan/WWAN_SLOT_INFO"
f1_keywords:
 - "wwan/WWAN_SLOT_INFO"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
- wwan.h
api_name:
- WWAN_SLOT_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_SLOT_INFO, *PWWAN_SLOT_INFO
---

# _WWAN_SLOT_INFO structure


## -description


The <b>WWAN_SLOT_INFO</b> structure represents the status of a specific SIM card slot on the modem.


## -struct-fields




### -field SlotIndex

The index of the slot being queried.


### -field State

The state of the slot being queried, a member of the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_uiccslot_state">WWAN_UICCSLOT_STATE</a> enumeration that represents a summary of both the slot and the card state.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-slot-info-status">NDIS_STATUS_WWAN_SLOT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_slot_info">NDIS_WWAN_SLOT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-slot-info-status">OID_WWAN_SLOT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_uiccslot_state">WWAN_UICCSLOT_STATE</a>
 

 

