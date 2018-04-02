---
UID: NS:wwan._WWAN_CDMA_MRL_INFO
title: "_WWAN_CDMA_MRL_INFO"
author: windows-driver-content
description: The WWAN_CDMA_MRL_INFO structure represents information about a CDMA serving cell or neighboring cell.
old-location: netvista\wwan_cdma_mrl_info.htm
old-project: netvista
ms.assetid: D8633E80-C7A3-4050-8E8E-8AE459F905D5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_CDMA_MRL_INFO, PWWAN_CDMA_MRL_INFO, PWWAN_CDMA_MRL_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_CDMA_MRL_INFO, WWAN_CDMA_MRL_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_CDMA_MRL_INFO, netvista.wwan_cdma_mrl_info, wwan/PWWAN_CDMA_MRL_INFO, wwan/WWAN_CDMA_MRL_INFO"
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
-	WWAN_CDMA_MRL_INFO
product: Windows
targetos: Windows
req.typenames: WWAN_CDMA_MRL_INFO, *PWWAN_CDMA_MRL_INFO
req.product: Windows 10 or later.
---

# _WWAN_CDMA_MRL_INFO structure


## -description


The <b>WWAN_CDMA_MRL_INFO</b> structure represents information about a CDMA serving cell or neighboring cell.


## -struct-fields




### -field ServingCellFlag

Indicates whether this is a serving cell. A value of 1 indicates a serving cell, while a value of 0 indicates a neighboring cell. There may be more than one serving cell at a time (notably while in a call).


### -field NID

The Network ID (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field SID

The System ID (0-32767). Use 0xFFFFFFFF when this information is not available.


### -field BaseStationId

The Base Station ID (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field BaseLatitude

The Base Station Latitude (0-4194303). This is encoded in units of 0.25 seconds, expressed in two’s complement representation within the low 22 bits of the DWORD. As a signed value, North latitudes are positive. Use 0xFFFFFFFF when this information is not available.


### -field BaseLongitude

The Base Station Longitude (0-8388607). This is encoded in units of 0.25 seconds, expressed in two’s complement representation within the low 23 bits of the DWORD. As a signed value, East longitudes are positive. Use 0xFFFFFFFF when this information is not available.


### -field RefPn

The Base Station PN Number (0-511). Use 0xFFFFFFFF when this information is not available.


### -field GPSSeconds

The GPS seconds, or the time at which this arrived from the base station. Use 0xFFFFFFFF when this information is not available.


### -field PilotStrength

The Signal Strength of the pilot (0-63). Use 0xFFFFFFFF when this information is not available.


## -remarks



<b>WWAN_CDMA_MRL_INFO</b> is designed for the CDMA2000 network type. There can be more than one CDMA2000 serving cell at the same time. Both serving cells and neighboring cells will be returned in the same list. The <b>ServingCellFlag</b> member indicates whether a cell is a serving cell or not.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://msdn.microsoft.com/66460B28-C2B4-4F05-A133-31A753AF9489">WWAN_BASE_STATIONS_INFO</a>



<a href="https://msdn.microsoft.com/A19B98B5-F2E5-4AF9-9D2B-A7DD47441656">WWAN_CDMA_MRL</a>
 

 

