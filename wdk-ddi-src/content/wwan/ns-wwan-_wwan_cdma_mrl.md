---
UID: NS:wwan._WWAN_CDMA_MRL
title: "_WWAN_CDMA_MRL"
author: windows-driver-content
description: The WWAN_CDMA_MRL structure represents the measured results list (MRL) of both serving and neighboring CDMA cells.
old-location: netvista\wwan_cdma_mrl.htm
old-project: netvista
ms.assetid: A19B98B5-F2E5-4AF9-9D2B-A7DD47441656
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_WWAN_CDMA_MRL, WWAN_CDMA_MRL structure [Network Drivers Starting with Windows Vista], *PWWAN_CDMA_MRL, netvista.wwan_cdma_mrl, wwan/PWWAN_CDMA_MRL, PWWAN_CDMA_MRL, WWAN_CDMA_MRL, wwan/WWAN_CDMA_MRL, PWWAN_CDMA_MRL structure pointer [Network Drivers Starting with Windows Vista]"
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
-	WWAN_CDMA_MRL
product: Windows
targetos: Windows
req.typenames: WWAN_CDMA_MRL, *PWWAN_CDMA_MRL
req.product: Windows 10 or later.
---

# _WWAN_CDMA_MRL structure


## -description


The <b>WWAN_CDMA_MRL</b> structure represents the measured results list (MRL) of both serving and neighboring CDMA cells.


## -syntax


````
typedef struct _WWAN_CDMA_MRL {
  ULONG ElementCount;
  BYTE  CDMAMrl[ANYSIZE_ARRAY];
} WWAN_CDMA_MRL, *PWWAN_CDMA_MRL;
````


## -struct-fields




### -field ElementCount

The count of MRL entries following this member.


### -field CDMAMrl

 




#### - CDMAMrl[ANYSIZE_ARRAY]

The array of MRL records, each specified as a <a href="..\wwan\ns-wwan-_wwan_cdma_mrl_info.md">WWAN_CDMA_MRL_INFO</a> structure.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_cdma_mrl_info.md">WWAN_CDMA_MRL_INFO</a>



<a href="..\wwan\ns-wwan-_wwan_base_stations_info.md">WWAN_BASE_STATIONS_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_CDMA_MRL structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

