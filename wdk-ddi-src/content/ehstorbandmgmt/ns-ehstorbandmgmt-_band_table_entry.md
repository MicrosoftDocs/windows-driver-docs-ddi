---
UID: NS:ehstorbandmgmt._BAND_TABLE_ENTRY
title: "_BAND_TABLE_ENTRY"
author: windows-driver-content
description: Banding information entries in BAND_TABLE are represented as BAND_TABLE_ENTRY structures. These entries contain location and security properties for a band configuration.
old-location: storage\band_table_entry.htm
old-project: storage
ms.assetid: 6956327E-5407-4771-9BB9-F59D752A5410
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PBAND_TABLE_ENTRY, BAND_TABLE_ENTRY, BAND_TABLE_ENTRY structure [Storage Devices], PBAND_TABLE_ENTRY, PBAND_TABLE_ENTRY structure pointer [Storage Devices], _BAND_TABLE_ENTRY, ehstorbandmgmt/BAND_TABLE_ENTRY, ehstorbandmgmt/PBAND_TABLE_ENTRY, storage.band_table_entry"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
-	EhStorBandMgmt.h
api_name:
-	BAND_TABLE_ENTRY
product: Windows
targetos: Windows
req.typenames: BAND_TABLE_ENTRY, *PBAND_TABLE_ENTRY
---

# _BAND_TABLE_ENTRY structure


## -description


Banding information entries in <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table.md">BAND_TABLE</a> are represented as <b>BAND_TABLE_ENTRY</b> structures. These entries contain location and security properties for a band configuration.


## -syntax


````
typedef struct _BAND_TABLE_ENTRY {
  ULONG              BandId;
  BAND_LOCATION_INFO LocationInfo;
  BAND_SECURITY_INFO SecurityInfo;
} BAND_TABLE_ENTRY, *PBAND_TABLE_ENTRY;
````


## -struct-fields




### -field BandId

The band identifier for a configured band on a storage device.


### -field LocationInfo

The band location information.


### -field SecurityInfo

The band security information. This includes encryption algorithm information when selected in <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a>.


## -see-also

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a>



<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a>



<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table.md">BAND_TABLE</a>



<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_location_info.md">BAND_LOCATION_INFO</a>



 

 


