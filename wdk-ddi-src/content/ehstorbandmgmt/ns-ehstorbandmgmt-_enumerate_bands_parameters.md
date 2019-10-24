---
UID: NS:ehstorbandmgmt._ENUMERATE_BANDS_PARAMETERS
title: _ENUMERATE_BANDS_PARAMETERS (ehstorbandmgmt.h)
description: The ENUMERATE_BANDS_PARAMETERS structure is used to select which band information entries are selected for return from an IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request.
old-location: storage\enumerate_bands_parameters.htm
tech.root: storage
ms.assetid: A493EF45-AA62-43FE-8E19-613B66FA0D83
ms.date: 03/29/2018
ms.keywords: "*PENUMERATE_BANDS_PARAMETERS, ENUMBANDS_ENUM_ALL_BANDS, ENUMBANDS_REPORT_CRYPTO_ALGO, ENUMERATE_BANDS_PARAMETERS, ENUMERATE_BANDS_PARAMETERS structure [Storage Devices], PENUMERATE_BANDS_PARAMETERS, PENUMERATE_BANDS_PARAMETERS structure pointer [Storage Devices], _ENUMERATE_BANDS_PARAMETERS, ehstorbandmgmt/ENUMERATE_BANDS_PARAMETERS, ehstorbandmgmt/PENUMERATE_BANDS_PARAMETERS, storage.enumerate_bands_parameters"
ms.topic: struct
f1_keywords:
 - "ehstorbandmgmt/ENUMERATE_BANDS_PARAMETERS"
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
- ENUMERATE_BANDS_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: ENUMERATE_BANDS_PARAMETERS, *PENUMERATE_BANDS_PARAMETERS
---

# _ENUMERATE_BANDS_PARAMETERS structure


## -description


The <b>ENUMERATE_BANDS_PARAMETERS</b> structure is used to select which band information entries are selected for return from an  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a> request.


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(ENUMERATE_BANDS_PARAMETERS).


### -field Flags

Band enumeration flags. This value is a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="ENUMBANDS_ENUM_ALL_BANDS"></a><a id="enumbands_enum_all_bands"></a><dl>
<dt><b>ENUMBANDS_ENUM_ALL_BANDS</b></dt>
</dl>
</td>
<td width="60%">
All bands are returned. When this flag is set, the <b>BandId</b>, <b>BandStart</b>, and <b>BandSize</b> members are ignored.

</td>
</tr>
<tr>
<td width="40%"><a id="ENUMBANDS_REPORT_CRYPTO_ALGO"></a><a id="enumbands_report_crypto_algo"></a><dl>
<dt><b>ENUMBANDS_REPORT_CRYPTO_ALGO</b></dt>
</dl>
</td>
<td width="60%">
Include media encryption algorithm information in the <b>SecurityInfo</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table_entry">BAND_TABLE_ENTRY</a>.

</td>
</tr>
</table>
 


### -field Reserved

Reserved.


### -field BandId

The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.


### -field BandStart

The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.


### -field BandSize

An optional band size match value in bytes. If <b>BandSize</b> == 0 and <b>BandId</b> == –1, then <b>BandStart</b> is the only match value for selecting a band. Otherwise, a band at or after <b>BandStart</b> and matching  <b>BandSize</b> exactly is selected.


## -remarks



When <b>ENUMBANDS_ENUM_ALL_BANDS</b> is not set in <b>Flags</b>, a selection attempt is made to match a single band. A single band match is made based on the values in <b>BandID</b>, <b>BandStart</b>, and <b>BandSize</b>. Precedence is given to <b>BandID</b> for band selection. If <b>BandID</b> > 0 and  <b>BandID</b> < <b>MaxBandCount</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a> If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <b>BAND_MANAGEMENT_CAPABILITIES</b>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == –1, then <b>BandStart</b> and <b>BandSize</b> are used as  match criteria to select a band.

When <b>BandStart</b> and <b>BandSize</b> are used to match a band, the first band configured at or after the <b>BandStart</b> location having the exact size of  <b>BandSize</b> is returned. If <b>BandSize</b> == 0, when <b>BandStart</b> is valid, then the first band configured at or after <b>BandStart</b> is returned.

If <b>BandID</b> == 0 or no bands are configured and <b>Flags</b> is not set to ENUMBANDS_ENUM_ALL_BANDS, then the global band for the entire device is returned.

<b>BandStart</b> and <b>BandSize</b> are not valid unless their values, in bytes, are exact multiples of the sector size of the underlying storage device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table">BAND_TABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table_entry">BAND_TABLE_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>
 

 

