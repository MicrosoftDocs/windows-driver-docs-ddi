---
UID: NS:wwan._WWAN_LTE_MRL_INFO
title: "_WWAN_LTE_MRL_INFO"
author: windows-driver-content
description: The WWAN_LTE_MRL_INFO structure represents information about a neighboring LTE cell.
old-location: netvista\wwan_lte_mrl_info.htm
old-project: netvista
ms.assetid: 49C3D862-EB78-4C44-A7B7-CE15E79EB021
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PWWAN_LTE_MRL_INFO structure pointer [Network Drivers Starting with Windows Vista], _WWAN_LTE_MRL_INFO, WWAN_LTE_MRL_INFO, PWWAN_LTE_MRL_INFO, wwan/WWAN_LTE_MRL_INFO, WWAN_LTE_MRL_INFO structure [Network Drivers Starting with Windows Vista], *PWWAN_LTE_MRL_INFO, wwan/PWWAN_LTE_MRL_INFO, netvista.wwan_lte_mrl_info
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
-	WWAN_LTE_MRL_INFO
product: Windows
targetos: Windows
req.typenames: "*PWWAN_LTE_MRL_INFO, WWAN_LTE_MRL_INFO"
req.product: Windows 10 or later.
---

# _WWAN_LTE_MRL_INFO structure


## -description


The <b>WWAN_LTE_MRL_INFO</b> structure represents information about a neighboring LTE cell.


## -syntax


````
typedef struct _WWAN_LTE_MRL_INFO {
  ULONG ProviderIdOffset;
  ULONG ProviderIdSize;
  ULONG CellId;
  ULONG EARFCN;
  ULONG PhysicalCellId;
  ULONG TAC;
  ULONG RSRP;
  ULONG RSRQ;
  BYTE  Data[ANYSIZE_ARRAY];
} WWAN_LTE_MRL_INFO, *PWWAN_LTE_MRL_INFO;
````


## -struct-fields




### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.


### -field ProviderIdSize

The size, in bytes, used for <i>ProviderId</i>.


### -field CellId

The Cell ID (0-268435455). Use 0xFFFFFFFF when this information is not available.


### -field EARFCN

The Radio Frequency Channel Number of the serving cell (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field PhysicalCellId

The Physical Cell ID (0-503). Use 0xFFFFFFFF when this information is not available.


### -field TAC

The Tracking Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field RSRP

The Average Reference Signal Received Power. The range is -140 to -44, in units of 1dBm. Use 0xFFFFFFFF when this information is not available.


### -field RSRQ

The Average Reference Signal Received Quality. The range is -20 to -3, in units of 1dBm. Use 0xFFFFFFFF when this information is not available.


### -field Data

 




#### - Data[ANYSIZE_ARRAY]

The data buffer containing <i>ProviderId</i>.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_base_stations_info.md">WWAN_BASE_STATIONS_INFO</a>



<a href="..\wwan\ns-wwan-_wwan_lte_mrl.md">WWAN_LTE_MRL</a>



<a href="..\wwan\ns-wwan-_wwan_lte_serving_cell_info.md">WWAN_LTE_SERVING_CELL_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_LTE_MRL_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

