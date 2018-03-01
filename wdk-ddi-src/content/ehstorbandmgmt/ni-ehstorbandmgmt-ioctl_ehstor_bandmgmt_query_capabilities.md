---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
title: IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
author: windows-driver-content
description: The IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES request retrieves the banded security capabilities for a storage device. The IOCTL returns the capabilities as a BAND_MANAGEMENT_CAPABILITIES structure in the system buffer.
old-location: storage\ioctl_ehstor_bandmgmt_query_capabilities.htm
old-project: storage
ms.assetid: 16D035EF-2234-4D5A-8D19-8CF3BA8B3590
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES, IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES, storage.ioctl_ehstor_bandmgmt_query_capabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</b> request retrieves the banded security capabilities for a storage device. The IOCTL returns the capabilities as a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a> structure in the system buffer.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>  structure.


### -output-buffer-length

The length of a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>  structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




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

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

