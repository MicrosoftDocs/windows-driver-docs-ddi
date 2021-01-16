---
UID: NS:ehstorbandmgmt._BAND_TABLE_ENTRY
title: _BAND_TABLE_ENTRY (ehstorbandmgmt.h)
description: Banding information entries in BAND_TABLE are represented as BAND_TABLE_ENTRY structures. These entries contain location and security properties for a band configuration.
old-location: storage\band_table_entry.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["BAND_TABLE_ENTRY structure"]
ms.keywords: "*PBAND_TABLE_ENTRY, BAND_TABLE_ENTRY, BAND_TABLE_ENTRY structure [Storage Devices], PBAND_TABLE_ENTRY, PBAND_TABLE_ENTRY structure pointer [Storage Devices], _BAND_TABLE_ENTRY, ehstorbandmgmt/BAND_TABLE_ENTRY, ehstorbandmgmt/PBAND_TABLE_ENTRY, storage.band_table_entry"
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
targetos: Windows
req.typenames: BAND_TABLE_ENTRY, *PBAND_TABLE_ENTRY
f1_keywords:
 - _BAND_TABLE_ENTRY
 - ehstorbandmgmt/_BAND_TABLE_ENTRY
 - PBAND_TABLE_ENTRY
 - ehstorbandmgmt/PBAND_TABLE_ENTRY
 - BAND_TABLE_ENTRY
 - ehstorbandmgmt/BAND_TABLE_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorBandMgmt.h
api_name:
 - _BAND_TABLE_ENTRY
 - PBAND_TABLE_ENTRY
 - BAND_TABLE_ENTRY
---

# _BAND_TABLE_ENTRY structure


## -description

Banding information entries in <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table">BAND_TABLE</a> are represented as <b>BAND_TABLE_ENTRY</b> structures. These entries contain location and security properties for a band configuration.

## -struct-fields

### -field BandId

The band identifier for a configured band on a storage device.

### -field LocationInfo

The band location information.

### -field SecurityInfo

The band security information. This includes encryption algorithm information when selected in <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_enumerate_bands_parameters">ENUMERATE_BANDS_PARAMETERS</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_location_info">BAND_LOCATION_INFO</a>



<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_security_info">BAND_SECURITY_INFO</a>



<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table">BAND_TABLE</a>



<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_enumerate_bands_parameters">ENUMERATE_BANDS_PARAMETERS</a>

