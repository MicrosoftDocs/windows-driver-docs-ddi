---
UID: NS:ehstorbandmgmt._SET_BAND_METADATA_PARAMETERS
title: "_SET_BAND_METADATA_PARAMETERS"
author: windows-driver-content
description: The metadata for a configured band is set to the parameters in a SET_BAND_METADATA_PARAMETERS structure. This structure is input for a IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA request.
old-location: storage\set_band_metadata_parameters.htm
tech.root: storage
ms.assetid: 3FCCFFE1-C341-4C8D-8EEC-E07C7ECFC317
ms.date: 3/29/2018
ms.keywords: "*PSET_BAND_METADATA_PARAMETERS, PSET_BAND_METADATA_PARAMETERS, PSET_BAND_METADATA_PARAMETERS structure pointer [Storage Devices], SET_BAND_METADATA_PARAMETERS, SET_BAND_METADATA_PARAMETERS structure [Storage Devices], _SET_BAND_METADATA_PARAMETERS, ehstorbandmgmt/PSET_BAND_METADATA_PARAMETERS, ehstorbandmgmt/SET_BAND_METADATA_PARAMETERS, storage.set_band_metadata_parameters"
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
-	SET_BAND_METADATA_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: SET_BAND_METADATA_PARAMETERS, *PSET_BAND_METADATA_PARAMETERS
---

# _SET_BAND_METADATA_PARAMETERS structure


## -description


The metadata for a configured band is set to the parameters in a <b>SET_BAND_METADATA_PARAMETERS</b> structure. This structure is input for a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451401">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a> request.


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(SET_BAND_METADATA_PARAMETERS).


### -field BandId

The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.


### -field BandStart

The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.


### -field MetadataOffset

The offset from the start of the band metadata property  to set the new   data.


### -field MetadataSize

The length of metadata bytes to set. This size is limited by the value of <b>MetadataOffset</b> subtracted from the <b>BandMetadataSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439563">BAND_MANAGEMENT_CAPABILITIES</a> structure.


### -field BufferOffset

The offset, in bytes, from the beginning of <b>SET_BAND_METADATA_PARAMETERS </b> to the location of the new metadata.


### -field AuthKeyOffset

The offset, in bytes, of an  <b> AUTH_KEY</b> structure containing the authorization key for the band. The offset is from the beginning of <b>SET_BAND_METADATA_PARAMETERS</b>. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _AUTH_KEY
{
    ULONG   KeySize;
    UCHAR   Key[ANYSIZE_ARRAY];
} AUTH_KEY;</pre>
</td>
</tr>
</table></span></div>




#### KeySize

Size of the key, in bytes, of the key data at <b>Key</b>. If <b>KeySize</b> is set to 0, a default key is used.



#### Key

A variable-length byte array that contains the key data.

To specify a default authentication key to the band, set   <b>AuthKeyOffset</b> = <b>EHSTOR_BANDMGR_NO_KEY</b>.


## -remarks



 Precedence is given to <b>BandID</b> for band selection. If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439563">BAND_MANAGEMENT_CAPABILITIES</a>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == -1, then <b>BandStart</b> is used as  the match criteria to select a band. If no band matches either selection criteria, then STATUS_INVALID_PARAMETER is returned in the <i>IoStatus</i> block for <a href="https://msdn.microsoft.com/library/windows/hardware/hh451401">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a>.

If <b>BandID</b> and <b>BandStart</b> are both set to –1,  then the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451401">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a> sets metadata for the global band.

The size of the  band metadata store is found in the <b>BandMetadataSize</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439563">BAND_MANAGEMENT_CAPABILITIES</a>. This structure is returned from a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451390">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a> request.

The new metadata to set for the band is included in the system buffer for  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451401">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a> request and follows this structure at <b>BufferOffset</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439563">BAND_MANAGEMENT_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451390">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451401">IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</a>
 

 

