---
UID: NS:ehstorbandmgmt._ENUMERATE_BANDS_PARAMETERS
title: "_ENUMERATE_BANDS_PARAMETERS"
author: windows-driver-content
description: The ENUMERATE_BANDS_PARAMETERS structure is used to select which band information entries are selected for return from an IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request.
old-location: storage\enumerate_bands_parameters.htm
old-project: storage
ms.assetid: A493EF45-AA62-43FE-8E19-613B66FA0D83
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PENUMERATE_BANDS_PARAMETERS structure pointer [Storage Devices], _ENUMERATE_BANDS_PARAMETERS, ehstorbandmgmt/ENUMERATE_BANDS_PARAMETERS, PENUMERATE_BANDS_PARAMETERS, ENUMERATE_BANDS_PARAMETERS structure [Storage Devices], *PENUMERATE_BANDS_PARAMETERS, ENUMBANDS_ENUM_ALL_BANDS, ehstorbandmgmt/PENUMERATE_BANDS_PARAMETERS, ENUMERATE_BANDS_PARAMETERS, ENUMBANDS_REPORT_CRYPTO_ALGO, storage.enumerate_bands_parameters
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
-	ENUMERATE_BANDS_PARAMETERS
product: Windows
targetos: Windows
req.typenames: ENUMERATE_BANDS_PARAMETERS, *PENUMERATE_BANDS_PARAMETERS
---

# _ENUMERATE_BANDS_PARAMETERS structure


## -description


The <b>ENUMERATE_BANDS_PARAMETERS</b> structure is used to select which band information entries are selected for return from an  <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands.md">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a> request.


## -syntax


````
typedef struct _ENUMERATE_BANDS_PARAMETERS {
  ULONG         StructSize;
  ULONG         Flags;
  ULONG         Reserved;
  ULONG         BandId;
  LARGE_INTEGER BandStart;
  LARGE_INTEGER BandSize;
} ENUMERATE_BANDS_PARAMETERS, *PENUMERATE_BANDS_PARAMETERS;
````


## -struct-fields




#### - StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(ENUMERATE_BANDS_PARAMETERS).


#### - Flags

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
Include media encryption algorithm information in the <b>SecurityInfo</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table_entry.md">BAND_TABLE_ENTRY</a>.

</td>
</tr>
</table> 


#### - Reserved

Reserved.


#### - BandId

The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.


#### - BandStart

The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.


#### - BandSize

An optional band size match value in bytes. If <b>BandSize</b> == 0 and <b>BandId</b> == –1, then <b>BandStart</b> is the only match value for selecting a band. Otherwise, a band at or after <b>BandStart</b> and matching  <b>BandSize</b> exactly is selected.


## -remarks


When <b>ENUMBANDS_ENUM_ALL_BANDS</b> is not set in <b>Flags</b>, a selection attempt is made to match a single band. A single band match is made based on the values in <b>BandID</b>, <b>BandStart</b>, and <b>BandSize</b>. Precedence is given to <b>BandID</b> for band selection. If <b>BandID</b> &gt; 0 and  <b>BandID</b> &lt; <b>MaxBandCount</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a> If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <b>BAND_MANAGEMENT_CAPABILITIES</b>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == –1, then <b>BandStart</b> and <b>BandSize</b> are used as  match criteria to select a band.

When <b>BandStart</b> and <b>BandSize</b> are used to match a band, the first band configured at or after the <b>BandStart</b> location having the exact size of  <b>BandSize</b> is returned. If <b>BandSize</b> == 0, when <b>BandStart</b> is valid, then the first band configured at or after <b>BandStart</b> is returned.

If <b>BandID</b> == 0 or no bands are configured and <b>Flags</b> is not set to ENUMBANDS_ENUM_ALL_BANDS, then the global band for the entire device is returned.

<b>BandStart</b> and <b>BandSize</b> are not valid unless their values, in bytes, are exact multiples of the sector size of the underlying storage device.



## -see-also

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table.md">BAND_TABLE</a>

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table_entry.md">BAND_TABLE_ENTRY</a>

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>

<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands.md">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ENUMERATE_BANDS_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

