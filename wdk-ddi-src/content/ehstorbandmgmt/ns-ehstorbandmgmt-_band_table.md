---
UID: NS:ehstorbandmgmt._BAND_TABLE
title: "_BAND_TABLE"
author: windows-driver-content
description: The BAND_TABLE structure contains the table of bands returned from an IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request.
old-location: storage\band_table.htm
old-project: storage
ms.assetid: 2714E346-6BDD-49EF-9820-6B82F8F29380
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: BAND_TABLE, BAND_TABLE structure [Storage Devices], PBAND_TABLE, PBAND_TABLE structure pointer [Storage Devices], *PBAND_TABLE, _BAND_TABLE, ehstorbandmgmt/PBAND_TABLE, ehstorbandmgmt/BAND_TABLE, storage.band_table
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	EhStorBandMgmt.h
apiname:
-	BAND_TABLE
product: Windows
targetos: Windows
req.typenames: BAND_TABLE, *PBAND_TABLE
---

# _BAND_TABLE structure


## -description


The <b>BAND_TABLE</b> structure contains the table of bands returned from an <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands.md">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a> request. The bands in the band table are selected by a match condition sent as input for <b>IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</b> in the <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a> structure.


## -syntax


````
typedef struct _BAND_TABLE {
  ULONG StructSize;
  ULONG BandTableOffset;
  ULONG BandTableEntryCount;
  ULONG BandTableEntrySize;
} BAND_TABLE, *PBAND_TABLE;
````


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(BAND_TABLE).


### -field BandTableOffset

The offset, in bytes, to the start of an array of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table_entry.md">BAND_TABLE_ENTRY</a> structures.


### -field BandTableEntryCount

The number of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table_entry.md">BAND_TABLE_ENTRY</a> returned in the array at <b>BandTableOffset</b>.


### -field BandTableEntrySize

The size of each entry, in bytes, in the array at <b>BandTableOffset</b>. Instead of using the value of <b>sizeof</b>(BAND_TABLE_ENTRY), callers must use <b>BandTableEntrySize</b> when advancing to the next element in the band table array.


## -see-also

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table_entry.md">BAND_TABLE_ENTRY</a>



<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a>



<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table_entry.md">BAND_TABLE_ENTRY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20BAND_TABLE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

