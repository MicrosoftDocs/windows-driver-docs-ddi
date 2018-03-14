---
UID: NS:wwan._WWAN_SLOT_INFO
title: "_WWAN_SLOT_INFO"
author: windows-driver-content
description: The WWAN_SLOT_INFO structure represents the status of a specific SIM card slot on the modem.
old-location: netvista\wwan_slot_info_status.htm
old-project: netvista
ms.assetid: F45D253E-E7D7-4600-AF8C-6D4EB096030D
ms.author: windowsdriverdev
ms.date: 2/27/2018
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
product: Windows
targetos: Windows
req.typenames: WWAN_SLOT_INFO, *PWWAN_SLOT_INFO
req.product: Windows 10 or later.
---

# _WWAN_SLOT_INFO structure


## -description


The <b>WWAN_SLOT_INFO</b> structure represents the status of a specific SIM card slot on the modem.


## -syntax


````
typedef struct _WWAN_SLOT_INFO {
  ULONG               SlotIndex;
  WWAN_UICCSLOT_STATE State;
} WWAN_SLOT_INFO, *PWWAN_SLOT_INFO;
````


## -struct-fields




### -field SlotIndex

The index of the slot being queried.


### -field State

The state of the slot being queried, a member of the  <a href="..\wwan\ne-wwan-_wwan_uiccslot_state.md">WWAN_UICCSLOT_STATE</a> enumeration that represents a summary of both the slot and the card state.


## -see-also

<a href="..\wwan\ne-wwan-_wwan_uiccslot_state.md">WWAN_UICCSLOT_STATE</a>



<a href="https://msdn.microsoft.com/FA1E16E4-56A3-4401-875F-D75DD01FE75D">NDIS_STATUS_WWAN_SLOT_INFO</a>



<a href="https://msdn.microsoft.com/6267D480-5055-4A7A-B2A0-F4DF9154DCD7">OID_WWAN_SLOT_INFO</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_slot_info.md">NDIS_WWAN_SLOT_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SLOT_INFO structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

