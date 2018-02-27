---
UID: NS:wwan._WWAN_CDMA_MRL_INFO
title: "_WWAN_CDMA_MRL_INFO"
author: windows-driver-content
description: The WWAN_CDMA_MRL_INFO structure represents information about a CDMA serving cell or neighboring cell.
old-location: netvista\wwan_cdma_mrl_info.htm
old-project: netvista
ms.assetid: D8633E80-C7A3-4050-8E8E-8AE459F905D5
ms.author: windowsdriverdev
ms.date: 2/16/2018
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


## -syntax


````
typedef struct _WWAN_CDMA_MRL_INFO {
  ULONG ServingCellFlag;
  ULONG NID;
  ULONG SID;
  ULONG BaseStationId;
  ULONG BaseLatitude;
  ULONG BaseLongitude;
  ULONG RefPn;
  ULONG GPSSeconds;
  ULONG PilotStrength;
} WWAN_CDMA_MRL_INFO, *PWWAN_CDMA_MRL_INFO;
````


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

<a href="..\wwan\ns-wwan-_wwan_base_stations_info.md">WWAN_BASE_STATIONS_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="..\wwan\ns-wwan-_wwan_cdma_mrl.md">WWAN_CDMA_MRL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_CDMA_MRL_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

