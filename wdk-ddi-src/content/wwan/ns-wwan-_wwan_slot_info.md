---
UID: NS:wwan._WWAN_SLOT_INFO
title: "_WWAN_SLOT_INFO"
author: windows-driver-content
description: The WWAN_SLOT_INFO structure represents the status of a specific SIM card slot on the modem.
old-location: netvista\wwan_slot_info_status.htm
old-project: netvista
ms.assetid: F45D253E-E7D7-4600-AF8C-6D4EB096030D
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_SLOT_INFO, PWWAN_SLOT_INFO, PWWAN_SLOT_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_SLOT_INFO, WWAN_SLOT_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_SLOT_INFO, netvista.wwan_slot_info_status, wwan/PWWAN_SLOT_INFO, wwan/WWAN_SLOT_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_SLOT_INFO
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

The state of the slot being queried, a member of the  <a href="https://msdn.microsoft.com/63A3C2AA-6EBF-469D-933A-C51F5EC31C47">WWAN_UICCSLOT_STATE</a> enumeration that represents a summary of both the slot and the card state.


## -see-also




<a href="https://msdn.microsoft.com/FA1E16E4-56A3-4401-875F-D75DD01FE75D">NDIS_STATUS_WWAN_SLOT_INFO</a>



<a href="https://msdn.microsoft.com/21D9DE55-2A26-467A-B119-8AFD4B47A4FD">NDIS_WWAN_SLOT_INFO</a>



<a href="https://msdn.microsoft.com/6267D480-5055-4A7A-B2A0-F4DF9154DCD7">OID_WWAN_SLOT_INFO</a>



<a href="https://msdn.microsoft.com/63A3C2AA-6EBF-469D-933A-C51F5EC31C47">WWAN_UICCSLOT_STATE</a>
 

 

