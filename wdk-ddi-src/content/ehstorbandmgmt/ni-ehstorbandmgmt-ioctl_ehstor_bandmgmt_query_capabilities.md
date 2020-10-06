---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
title: IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES (ehstorbandmgmt.h)
description: The IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES request retrieves the banded security capabilities for a storage device. The IOCTL returns the capabilities as a BAND_MANAGEMENT_CAPABILITIES structure in the system buffer.
old-location: storage\ioctl_ehstor_bandmgmt_query_capabilities.htm
tech.root: storage
ms.assetid: 16D035EF-2234-4D5A-8D19-8CF3BA8B3590
ms.date: 03/29/2018
keywords: ["IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES IOCTL"]
ms.keywords: IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES, IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES control, IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES, storage.ioctl_ehstor_bandmgmt_query_capabilities
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
req.typenames: 
f1_keywords:
 - IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
 - ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorBandMgmt.h
api_name:
 - IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
---

# IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES IOCTL


## -description

The <b>IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</b> request retrieves the banded security capabilities for a storage device. The IOCTL returns the capabilities as a <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a> structure in the system buffer.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The output buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>  structure.

### -output-buffer-length

The length of a <a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>  structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. One of the following values can be returned in the <b>Status</b> field. 

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The device supports band management and the security capabilities are returned in the system buffer.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_REQUEST</td>
<td>Band management is not supported on the storage device.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_STATE</td>
<td>The device provides band management support but not in its present configuration.</td>
</tr>
<tr>
<td>STATUS_BUFFER_OVERFLOW</td>
<td>A buffer is not provided or its size is set to zero. The required size is returned in the <b>Information</b> field.</td>
</tr>
<tr>
<td>STATUS_BUFFER_TOO_SMALL</td>
<td>The buffer size is too small to return the output.</td>
</tr>
</table>

## -remarks

A driver or application can query for the necessary output buffer size by setting the output buffer for the request to NULL and the output size to 0. The <b>IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</b> request will return with the <b>Status</b> field of the <i>IoStatus</i> block set to STATUS_BUFFER_OVERFLOW and the <b>Information</b> field will contain the required buffer size.

## -see-also

<a href="/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_management_capabilities">BAND_MANAGEMENT_CAPABILITIES</a>