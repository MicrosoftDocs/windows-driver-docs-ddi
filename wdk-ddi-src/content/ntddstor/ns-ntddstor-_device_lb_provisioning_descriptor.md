---
UID: NS:ntddstor._DEVICE_LB_PROVISIONING_DESCRIPTOR
title: "_DEVICE_LB_PROVISIONING_DESCRIPTOR"
author: windows-driver-content
description: The DEVICE_LB_PROVISIONING_DESCRIPTOR structure is one of the query result structures returned from an IOCTL_STORAGE_QUERY_PROPERTY request. This structure contains the thin provisioning capabilities for a storage device.
old-location: storage\device_lb_provisioning_descriptor.htm
old-project: storage
ms.assetid: E7287A50-2BB8-4D11-AB9B-6E65EEDD698D
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/PDEVICE_LB_PROVISIONING_DESCRIPTOR, DEVICE_LB_PROVISIONING_DESCRIPTOR structure [Storage Devices], *PDEVICE_LB_PROVISIONING_DESCRIPTOR, PDEVICE_LB_PROVISIONING_DESCRIPTOR, PDEVICE_LB_PROVISIONING_DESCRIPTOR structure pointer [Storage Devices], ntddstor/DEVICE_LB_PROVISIONING_DESCRIPTOR, _DEVICE_LB_PROVISIONING_DESCRIPTOR, storage.device_lb_provisioning_descriptor, DEVICE_LB_PROVISIONING_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	ntddstor.h
apiname:
-	DEVICE_LB_PROVISIONING_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DEVICE_LB_PROVISIONING_DESCRIPTOR, *PDEVICE_LB_PROVISIONING_DESCRIPTOR
---

# _DEVICE_LB_PROVISIONING_DESCRIPTOR structure


## -description


The <b>DEVICE_LB_PROVISIONING_DESCRIPTOR</b> structure is one of the query result structures returned from an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request. This structure contains the thin provisioning capabilities for a storage device.


## -syntax


````
typedef struct _DEVICE_LB_PROVISIONING_DESCRIPTOR {
  ULONG     Version;
  ULONG     Size;
  UCHAR     ThinProvisioningEnabled  :1;
  UCHAR     ThinProvisioningReadZeros  :1;
  UCHAR     AnchorSupported  :3;
  UCHAR     UnmapGranularityAlignmentValid  :1;
  UCHAR     Reserverd0  :2;
  UCHAR     Reserverd1[7];
  ULONGLONG OptimalUnmapGranularity;
  ULONGLONG UnmapGranularityAlignment;
  ULONG     MaxUnmapLbaCount;
  ULONG     MaxUnmapBlockDescriptorCount;
} DEVICE_LB_PROVISIONING_DESCRIPTOR, *PDEVICE_LB_PROVISIONING_DESCRIPTOR;
````


## -struct-fields




### -field Version

The version of this structure.


### -field Size

The size of this structure. This is set to <b>sizeof</b>(DEVICE_LB_PROVISIONING_DESCRIPTOR).


### -field ThinProvisioningEnabled

The thin provisioning–enabled status.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Thin provisioning is disabled.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Thin provisioning is enabled.

</td>
</tr>
</table> 


### -field ThinProvisioningReadZeros

Reads to unmapped regions return zeros.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Data read from unmapped regions is undefined.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Reads return zeros.

</td>
</tr>
</table> 


### -field AnchorSupported

Support for the anchored LBA mapping state.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
The anchored LBA mapping state is not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
The anchored LBA mapping state is supported.

</td>
</tr>
</table> 


### -field UnmapGranularityAlignmentValid

The validity of unmap granularity alignment for the device.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Unmap granularity alignment is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Unmap granularity alignment is valid.

</td>
</tr>
</table> 


### -field Reserved0

 


### -field Reserved1

 


### -field OptimalUnmapGranularity

The optimal number of blocks for unmap granularity for the device.


### -field UnmapGranularityAlignment

The current value, in blocks, set for unmap granularity alignment on the device.   The value <b>UnmapGranularityAlignmentValid</b> indicates the validity of this member.


### -field MaxUnmapLbaCount

Maximum amount of LBAs that can be unmapped in a single UNMAP command, in units of logical blocks. This is valid only in Windows 10 and above.


### -field MaxUnmapBlockDescriptorCount

Maximum number of descriptors allowed in a single UNMAP command. This is valid only in Windows 10 and above.


#### - Reserverd0

Reserved.


#### - Reserverd1

Reserved.


## -remarks


This structure is returned in the system buffer from a <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request when the <b>PropertyId</b> member of <a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a> is set to <b>StorageDeviceLBProvisioningProperty</b>. 

The <b>DEVICE_LB_PROVISIONING_DESCRIPTOR</b> structure is written to the system buffer, <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>, with a value of <b>sizeof</b>(DEVICE_LB_PROVISIONING_DESCRIPTOR) set in <i>Parameters.DeviceIoControl.OutputBufferLength</i> for the current IRP stack location.

If <b>UnmapGranularityAlignmentValid</b> = 0,  then any code using <b>UnmapGranularityAlignment</b> should assume it has a value of 0.

If the underlying storage device is a SCSI device, unmapping capability can be queried. If the <b>TrimEnabled</b> member of the <a href="..\ntddstor\ns-ntddstor-_device_trim_descriptor.md">DEVICE_TRIM_DESCRIPTOR</a> structure is TRUE, UNMAP is supported. The <b>DEVICE_TRIM_DESCRIPTOR</b> structure is returned in the system buffer from a <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request when the <b>PropertyId</b> member of <a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a> is set to <b>StorageDeviceTrimProperty</b>.



## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_LB_PROVISIONING_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

