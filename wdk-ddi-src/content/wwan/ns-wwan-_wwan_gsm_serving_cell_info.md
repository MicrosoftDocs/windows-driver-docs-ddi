---
UID: NS:wwan._WWAN_GSM_SERVING_CELL_INFO
title: "_WWAN_GSM_SERVING_CELL_INFO"
author: windows-driver-content
description: The WWAN_GSM_SERVING_CELL_INFO structure represents information about the GSM serving cell.
old-location: netvista\wwan_gsm_serving_cell_info.htm
old-project: netvista
ms.assetid: 37F6BD26-55F3-4E46-9C39-97A95B6FF5B1
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_GSM_SERVING_CELL_INFO, PWWAN_GSM_SERVING_CELL_INFO, PWWAN_GSM_SERVING_CELL_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_GSM_SERVING_CELL_INFO, WWAN_GSM_SERVING_CELL_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_GSM_SERVING_CELL_INFO, netvista.wwan_gsm_serving_cell_info, wwan/PWWAN_GSM_SERVING_CELL_INFO, wwan/WWAN_GSM_SERVING_CELL_INFO"
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
-	WWAN_GSM_SERVING_CELL_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_GSM_SERVING_CELL_INFO, *PWWAN_GSM_SERVING_CELL_INFO
---

# _WWAN_GSM_SERVING_CELL_INFO structure


## -description


The <b>WWAN_GSM_SERVING_CELL_INFO</b> structure represents information about the GSM serving cell.


## -struct-fields




### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.


### -field ProviderIdSize

The size, in bytes, used for <i>ProviderId</i>.


### -field LocationAreaCode

The Location Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field CellId

The Cell ID (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field TimingAdvance

The Timing Advance (0-255) in bit periods, where a bit period is 48/13µs. Use 0xFFFFFFFF when this information is not available.


### -field ARFCN

The Absolute Radio Frequency Channel Number of the serving cell (0-1023). Use 0xFFFFFFFF when this information is not available.


### -field BaseStationId

The Base Station ID - the base station color code and the network identity code. Use 0xFFFFFFFF when this information is not available.


### -field RxLevel

The received signal strength (RSS) of the serving cell (0-63), where

<pre class="syntax" xml:space="preserve"><code>X = 0, if RSS &lt; -110 dBm</code></pre>
<pre class="syntax" xml:space="preserve"><code>X = 63, if RSS &gt; -47 dBm</code></pre>
<pre class="syntax" xml:space="preserve"><code>X = integer [RSS + 110], if -110 &lt;= RSS &lt;= -47</code></pre>
Use 0xFFFFFFFF when this information is not available.


### -field Data

The data buffer containing <i>ProviderId</i>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://msdn.microsoft.com/66460B28-C2B4-4F05-A133-31A753AF9489">WWAN_BASE_STATIONS_INFO</a>



<a href="https://msdn.microsoft.com/ADEEB57F-79FF-4AA7-84AF-FED413E47057">WWAN_GSM_NMR</a>



<a href="https://msdn.microsoft.com/EF22D5C3-7A3B-4A96-A050-FCB71CA2C149">WWAN_GSM_NMR_INFO</a>
 

 

