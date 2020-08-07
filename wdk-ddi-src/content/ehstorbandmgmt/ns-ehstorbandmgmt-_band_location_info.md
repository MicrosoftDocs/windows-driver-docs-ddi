---
UID: NS:ehstorbandmgmt._BAND_LOCATION_INFO
title: _BAND_LOCATION_INFO (ehstorbandmgmt.h)
description: The BAND_LOCATION_INFO structure specifies the location information for a band table entry query.
old-location: storage\band_location_info.htm
tech.root: storage
ms.assetid: A9E28600-45B2-4082-917F-29B3237DEC84
ms.date: 03/29/2018
keywords: ["BAND_LOCATION_INFO structure"]
ms.keywords: "*PBAND_LOCATION_INFO, BAND_LOCATION_INFO, BAND_LOCATION_INFO structure [Storage Devices], PBAND_LOCATION_INFO, PBAND_LOCATION_INFO structure pointer [Storage Devices], _BAND_LOCATION_INFO, ehstorbandmgmt/BAND_LOCATION_INFO, ehstorbandmgmt/PBAND_LOCATION_INFO, storage.band_location_info"
f1_keywords:
 - "ehstorbandmgmt/BAND_LOCATION_INFO"
 - "BAND_LOCATION_INFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- EhStorBandMgmt.h
api_name:
- BAND_LOCATION_INFO
targetos: Windows
req.typenames: BAND_LOCATION_INFO, *PBAND_LOCATION_INFO
---

# _BAND_LOCATION_INFO structure


## -description


The <b>BAND_LOCATION_INFO</b> structure specifies the location information for a band table entry query.


## -struct-fields




### -field StructSize

The size of the structure in bytes. Set to <b>sizeof</b>(BAND_LOCATION_INFO).


### -field Reserved

Reserved.


### -field BandStart

The offset in bytes of this band location on the storage device. This value is always 0 for the global band.


### -field BandSize

The size in bytes of the band configured at this location. This value is set to the maximum size possible for the global band.


### -field Metadata

A metadata field used as a data area for a band management application.


## -remarks



<b>BandStart</b> and <b>BandSize</b> must be a multiple of the sector size of the underlying storage device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table_entry">BAND_TABLE_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>
 

 

