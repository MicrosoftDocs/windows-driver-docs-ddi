---
UID: NS:wwan._WWAN_DEVICE_SLOT_MAPPING_INFO
title: _WWAN_DEVICE_SLOT_MAPPING_INFO (wwan.h)
description: The WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship in the MB device.
old-location: netvista\wwan_device_slot_mappings.htm
tech.root: netvista
ms.assetid: 48DD867C-1235-4955-A01E-FF46C850DA31
ms.date: 05/02/2018
ms.keywords: "*PWWAN_DEVICE_SLOT_MAPPING_INFO, PWWAN_DEVICE_SLOT_MAPPING_INFO, PWWAN_DEVICE_SLOT_MAPPING_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SLOT_MAPPING_INFO, WWAN_DEVICE_SLOT_MAPPING_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SLOT_MAPPING_INFO, netvista.wwan_device_slot_mappings, wwan/PWWAN_DEVICE_SLOT_MAPPING_INFO, wwan/WWAN_DEVICE_SLOT_MAPPING_INFO"
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
-	WWAN_DEVICE_SLOT_MAPPING_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SLOT_MAPPING_INFO, *PWWAN_DEVICE_SLOT_MAPPING_INFO
---

# _WWAN_DEVICE_SLOT_MAPPING_INFO structure


## -description


The WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship in the MB device.


## -struct-fields




### -field SlotMapListHeader

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a> has a new structure, <b>WwanStructSlotIndex</b>, which represents the slot index the <i>i-th</i> executor is mapped to (where 0 &lt;= i &lt;= (Number of mappings -1)).


## -see-also




<a href="https://msdn.microsoft.com/7825C20E-FB56-420D-B516-1ADA0C7C382E">NDIS_STATUS_WWAN_DEVICE_SLOT_MAPPING_INFO</a>



<a href="https://msdn.microsoft.com/18437B56-B84C-499B-8D4F-F65B5B8221A6">NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO</a>



<a href="https://msdn.microsoft.com/5DAE5A36-1A2B-46DF-8CF1-FAC8B98460A8">NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO</a>



<a href="https://msdn.microsoft.com/54AF3447-7918-49CE-945A-DC8DC1E78CBF">OID_WWAN_DEVICE_SLOT_MAPPING_INFO</a>
 

 

