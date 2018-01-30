---
UID: NS:wwan._WWAN_UICC_RESET_INFO
title: "_WWAN_UICC_RESET_INFO"
author: windows-driver-content
description: The WWAN_UICC_RESET_INFO structure represents the passthrough status of a modem miniport adapter for a UICC smart card.
old-location: netvista\wwan_uicc_reset_info.htm
old-project: netvista
ms.assetid: 1D53135F-3826-4546-A0AD-34697D186E8A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/PWWAN_UICC_RESET_INFO, wwan/WWAN_UICC_RESET_INFO, _WWAN_UICC_RESET_INFO, WWAN_UICC_RESET_INFO, PWWAN_UICC_RESET_INFO structure pointer [Network Drivers Starting with Windows Vista], *PWWAN_UICC_RESET_INFO, PWWAN_UICC_RESET_INFO, WWAN_UICC_RESET_INFO structure [Network Drivers Starting with Windows Vista], netvista.wwan_uicc_reset_info
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
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

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_uicc_reset_info.md">NDIS_WWAN_UICC_RESET_INFO</a>

<a href="..\wwan\ne-wwan-_wwan_uicc_passthrough_status.md">WWAN_UICC_PASSTHROUGH_STATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_UICC_RESET_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

