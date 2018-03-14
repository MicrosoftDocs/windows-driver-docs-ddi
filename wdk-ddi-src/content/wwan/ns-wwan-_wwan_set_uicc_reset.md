---
UID: NS:wwan._WWAN_SET_UICC_RESET
title: "_WWAN_SET_UICC_RESET"
author: windows-driver-content
description: The WWAN_SET_UICC_RESET structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a UICC smart card.
old-location: netvista\wwan_set_uicc_reset.htm
old-project: netvista
ms.assetid: 33711459-70C8-43D2-974D-B90EC0DD8ED6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_SET_UICC_RESET, PWWAN_SET_UICC_RESET, PWWAN_SET_UICC_RESET structure pointer [Network Drivers Starting with Windows Vista], WWAN_SET_UICC_RESET, WWAN_SET_UICC_RESET structure [Network Drivers Starting with Windows Vista], _WWAN_SET_UICC_RESET, netvista.wwan_set_uicc_reset, wwan/PWWAN_SET_UICC_RESET, wwan/WWAN_SET_UICC_RESET"
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
-	WWAN_SET_UICC_RESET
product: Windows
targetos: Windows
req.typenames: WWAN_SET_UICC_RESET, *PWWAN_SET_UICC_RESET
req.product: Windows 10 or later.
---

# _WWAN_SET_UICC_RESET structure


## -description


The <b>WWAN_SET_UICC_RESET</b> structure represents the passthrough action the MB host specifies for a modem miniport adapter after it resets a  UICC smart card.


## -syntax


````
typedef struct _WWAN_SET_UICC_RESET {
  WWAN_UICC_PASSTHROUGH_ACTION PassThroughAction;
} WWAN_SET_UICC_RESET, *PWWAN_SET_UICC_RESET;
````


## -struct-fields




### -field PassThroughAction

The passthrough action specified by the host. For more info, see <a href="..\wwan\ne-wwan-_wwan_uicc_passthrough_action.md">WWAN_UICC_PASSTHROUGH_ACTION</a>.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>



<a href="..\wwan\ne-wwan-_wwan_uicc_passthrough_action.md">WWAN_UICC_PASSTHROUGH_ACTION</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_set_uicc_reset.md">NDIS_WWAN_SET_UICC_RESET</a>



 

 


