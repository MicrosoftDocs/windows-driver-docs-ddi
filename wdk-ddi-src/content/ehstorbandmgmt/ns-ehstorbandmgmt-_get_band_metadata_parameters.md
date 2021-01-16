---
UID: NS:ehstorbandmgmt._GET_BAND_METADATA_PARAMETERS
title: _GET_BAND_METADATA_PARAMETERS (ehstorbandmgmt.h)
description: The metadata for a configured band is retrieved according to the parameters in a GET_BAND_METADATA_PARAMETERS structure. This structure is input for an IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA request.
old-location: storage\get_band_metadata_parameters.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["GET_BAND_METADATA_PARAMETERS structure"]
ms.keywords: "*PGET_BAND_METADATA_PARAMETERS, GET_BAND_METADATA_PARAMETERS, GET_BAND_METADATA_PARAMETERS structure [Storage Devices], PGET_BAND_METADATA_PARAMETERS, PGET_BAND_METADATA_PARAMETERS structure pointer [Storage Devices], _GET_BAND_METADATA_PARAMETERS, ehstorbandmgmt/GET_BAND_METADATA_PARAMETERS, ehstorbandmgmt/PGET_BAND_METADATA_PARAMETERS, storage.get_band_metadata_parameters"
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
req.typenames: GET_BAND_METADATA_PARAMETERS, *PGET_BAND_METADATA_PARAMETERS
f1_keywords:
 - _GET_BAND_METADATA_PARAMETERS
 - ehstorbandmgmt/_GET_BAND_METADATA_PARAMETERS
 - PGET_BAND_METADATA_PARAMETERS
 - ehstorbandmgmt/PGET_BAND_METADATA_PARAMETERS
 - GET_BAND_METADATA_PARAMETERS
 - ehstorbandmgmt/GET_BAND_METADATA_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorBandMgmt.h
api_name:
 - _GET_BAND_METADATA_PARAMETERS
 - PGET_BAND_METADATA_PARAMETERS
 - GET_BAND_METADATA_PARAMETERS
---

# _GET_BAND_METADATA_PARAMETERS structure


## -description

The metadata for a configured band is retrieved according to the parameters in a <b>GET_BAND_METADATA_PARAMETERS</b> structure. This structure is input for an <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_get_band_metadata"> IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a> request.

## -struct-fields

### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(GET_BAND_METADATA_PARAMETERS).

### -field BandId

The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.

### -field BandStart

The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.

### -field MetadataOffset

The offset from the start of the band metadata property  to retrieve  data from.

### -field MetadataSize

The length of metadata bytes to retrieve.

## -remarks

 Precedence is given to <b>BandID</b> for band selection.  If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == –1, then <b>BandStart</b> is used as  the match criteria to select a band. If no band matches either selection criteria, then STATUS_INVALID_PARAMETER is returned in the <i>IoStatus</i> block for <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_get_band_metadata">IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a>.

If <b>BandID</b> and <b>BandStart</b> are both set to –1,  then the <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_get_band_metadata">IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a> returns metadata for the global band.

If <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_get_band_metadata">IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a> was successful, <i>Parameters.DeviceIoControl.InputBufferLength</i> equals the value in <b>MetadataSize</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_get_band_metadata">IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</a>

