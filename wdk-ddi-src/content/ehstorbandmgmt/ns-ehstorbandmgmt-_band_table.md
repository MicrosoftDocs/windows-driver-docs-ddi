---
UID: NS:ehstorbandmgmt._BAND_TABLE
title: _BAND_TABLE (ehstorbandmgmt.h)
description: The BAND_TABLE structure contains the table of bands returned from an IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request.
old-location: storage\band_table.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["BAND_TABLE structure"]
ms.keywords: "*PBAND_TABLE, BAND_TABLE, BAND_TABLE structure [Storage Devices], PBAND_TABLE, PBAND_TABLE structure pointer [Storage Devices], _BAND_TABLE, ehstorbandmgmt/BAND_TABLE, ehstorbandmgmt/PBAND_TABLE, storage.band_table"
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
req.typenames: BAND_TABLE, *PBAND_TABLE
f1_keywords:
 - _BAND_TABLE
 - ehstorbandmgmt/_BAND_TABLE
 - PBAND_TABLE
 - ehstorbandmgmt/PBAND_TABLE
 - BAND_TABLE
 - ehstorbandmgmt/BAND_TABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorBandMgmt.h
api_name:
 - _BAND_TABLE
 - PBAND_TABLE
 - BAND_TABLE
---

# _BAND_TABLE structure


## -description

The <b>BAND_TABLE</b> structure contains the table of bands returned from an <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a> request. The bands in the band table are selected by a match condition sent as input for <b>IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</b> in the <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_enumerate_bands_parameters">ENUMERATE_BANDS_PARAMETERS</a> structure.

## -struct-fields

### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(BAND_TABLE).

### -field BandTableOffset

The offset, in bytes, to the start of an array of <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table_entry">BAND_TABLE_ENTRY</a> structures.

### -field BandTableEntryCount

The number of <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table_entry">BAND_TABLE_ENTRY</a> returned in the array at <b>BandTableOffset</b>.

### -field BandTableEntrySize

The size of each entry, in bytes, in the array at <b>BandTableOffset</b>. Instead of using the value of <b>sizeof</b>(BAND_TABLE_ENTRY), callers must use <b>BandTableEntrySize</b> when advancing to the next element in the band table array.

## -see-also

<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table_entry">BAND_TABLE_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_enumerate_bands_parameters">ENUMERATE_BANDS_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>

