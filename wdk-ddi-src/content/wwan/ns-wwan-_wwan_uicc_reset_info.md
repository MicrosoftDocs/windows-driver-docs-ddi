---
UID: NS:wwan._WWAN_UICC_RESET_INFO
title: "_WWAN_UICC_RESET_INFO"
author: windows-driver-content
description: The WWAN_UICC_RESET_INFO structure represents the passthrough status of a modem miniport adapter for a UICC smart card.
old-location: netvista\wwan_uicc_reset_info.htm
old-project: netvista
ms.assetid: 1D53135F-3826-4546-A0AD-34697D186E8A
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_UICC_RESET_INFO, PWWAN_UICC_RESET_INFO, PWWAN_UICC_RESET_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_UICC_RESET_INFO, WWAN_UICC_RESET_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_UICC_RESET_INFO, netvista.wwan_uicc_reset_info, wwan/PWWAN_UICC_RESET_INFO, wwan/WWAN_UICC_RESET_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	WWAN_UICC_RESET_INFO
product: Windows
targetos: Windows
req.typenames: WWAN_UICC_RESET_INFO, *PWWAN_UICC_RESET_INFO
req.product: Windows 10 or later.
---

# _WWAN_UICC_RESET_INFO structure


## -description


The <b>WWAN_UICC_RESET_INFO</b> structure represents the passthrough status of a modem miniport adapter for a UICC smart card.


## -syntax


````
typedef struct _WWAN_UICC_RESET_INFO {
  WWAN_UICC_PASSTHROUGH_STATUS PassThroughStatus;
} WWAN_UICC_RESET_INFO, *PWWAN_UICC_RESET_INFO;
````


## -struct-fields




### -field PassThroughStatus

The passthrough status of the miniport adapter. For more info, see <a href="..\wwan\ne-wwan-_wwan_uicc_passthrough_status.md">WWAN_UICC_PASSTHROUGH_STATUS</a>.


## -see-also

<a href="..\wwan\ne-wwan-_wwan_uicc_passthrough_status.md">WWAN_UICC_PASSTHROUGH_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_uicc_reset_info.md">NDIS_WWAN_UICC_RESET_INFO</a>



 

 


