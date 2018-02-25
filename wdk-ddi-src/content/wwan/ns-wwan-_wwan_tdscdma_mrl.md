---
UID: NS:wwan._WWAN_TDSCDMA_MRL
title: "_WWAN_TDSCDMA_MRL"
author: windows-driver-content
description: The WWAN_TDSCDMA_MRL structure represents the measured results list (MRL) of neighboring TDSCDMA cells.
old-location: netvista\wwan_tdscdma_mrl.htm
old-project: netvista
ms.assetid: D919EF5E-502C-4983-AFC5-F3F6E6CC8C3B
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PWWAN_TDSCDMA_MRL, ,, A, C, D, L, M, N, P, PWWAN_TDSCDMA_MRL, PWWAN_TDSCDMA_MRL structure pointer [Network Drivers Starting with Windows Vista], R, S, T, W, WWAN_TDSCDMA_MRL, WWAN_TDSCDMA_MRL structure [Network Drivers Starting with Windows Vista], _, _WWAN_TDSCDMA_MRL, netvista.wwan_tdscdma_mrl, wwan/PWWAN_TDSCDMA_MRL, wwan/WWAN_TDSCDMA_MRL"
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
-	WWAN_TDSCDMA_MRL
product: Windows
targetos: Windows
req.typenames: WWAN_TDSCDMA_MRL, *PWWAN_TDSCDMA_MRL
req.product: Windows 10 or later.
---

# _WWAN_TDSCDMA_MRL structure


## -description


The <b>WWAN_TDSCDMA_MRL</b> structure represents the measured results list (MRL) of neighboring TDSCDMA cells.


## -syntax


````
typedef struct _WWAN_TDSCDMA_MRL {
  ULONG ElementCount;
  BYTE  TDSCDMAMrl[ANYSIZE_ARRAY];
} WWAN_TDSCDMA_MRL, *PWWAN_TDSCDMA_MRL;
````


## -struct-fields




### -field ElementCount

The count of MRL entries following this member.


### -field TDSCDMAMrl

 




#### - TDSCDMAMrl[ANYSIZE_ARRAY]

The array of MRL records, each specified as a <a href="..\wwan\ns-wwan-_wwan_tdscdma_mrl_info.md">WWAN_TDSCDMA_MRL_INFO</a> structure.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_tdscdma_serving_cell_info.md">WWAN_TDSCDMA_SERVING_CELL_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="..\wwan\ns-wwan-_wwan_tdscdma_mrl_info.md">WWAN_TDSCDMA_MRL_INFO</a>



<a href="..\wwan\ns-wwan-_wwan_base_stations_info.md">WWAN_BASE_STATIONS_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_TDSCDMA_MRL structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

