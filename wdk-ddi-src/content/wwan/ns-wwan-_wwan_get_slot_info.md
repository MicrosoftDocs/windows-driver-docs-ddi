---
UID: NS:wwan._WWAN_GET_SLOT_INFO
title: "_WWAN_GET_SLOT_INFO"
author: windows-driver-content
description: The WWAN_GET_SLOT_INFO structure contains the slot index to specify which slot's status a query request is for.
old-location: netvista\wwan_get_slot_info_status.htm
old-project: netvista
ms.assetid: 62955CA4-8631-4A85-8E78-5A91A9DA0069
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_GET_SLOT_INFO, PWWAN_GET_SLOT_INFO, PWWAN_GET_SLOT_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_GET_SLOT_INFO, WWAN_GET_SLOT_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_GET_SLOT_INFO, netvista.wwan_get_slot_info_status, wwan/PWWAN_GET_SLOT_INFO, wwan/WWAN_GET_SLOT_INFO"
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
-	WWAN_GET_SLOT_INFO
product: Windows
targetos: Windows
req.typenames: WWAN_GET_SLOT_INFO, *PWWAN_GET_SLOT_INFO
req.product: Windows 10 or later.
---

# _WWAN_GET_SLOT_INFO structure


## -description


The WWAN_GET_SLOT_INFO structure contains the slot index to specify which slot's status a query request is for.


## -struct-fields




### -field SlotIndex

Represents the index of the SIM slot. <b>SlotIndex</b> can be mapped to either a physical or embedded SIM slot and may be expanded to soft SIM in the future.


## -see-also




<a href="https://msdn.microsoft.com/214AFAD3-B211-4D66-8CFC-58F8EB407B83">NDIS_WWAN_GET_SLOT_INFO</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_GET_SLOT_INFO structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

