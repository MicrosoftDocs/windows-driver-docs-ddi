---
UID: NS:ufs.UFS_DEVICE_HEALTH_DESCRIPTOR
title: UFS_DEVICE_HEALTH_DESCRIPTOR
author: windows-driver-content
description: The UFS_DEVICE_HEALTH_DESCRIPTOR structure describes the health of a device.
old-location: storage\ufs_device_health_descriptor.htm
old-project: storage
ms.assetid: 6B085DBB-2AAA-4170-A2B1-EA4D2C207A24
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUFS_DEVICE_HEALTH_DESCRIPTOR, PUFS_DEVICE_HEALTH_DESCRIPTOR, PUFS_DEVICE_HEALTH_DESCRIPTOR structure pointer [Storage Devices], UFS_DEVICE_HEALTH_DESCRIPTOR, UFS_DEVICE_HEALTH_DESCRIPTOR structure [Storage Devices], storage.ufs_device_health_descriptor, ufs/PUFS_DEVICE_HEALTH_DESCRIPTOR, ufs/UFS_DEVICE_HEALTH_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ufs.h
api_name:
-	UFS_DEVICE_HEALTH_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: UFS_DEVICE_HEALTH_DESCRIPTOR, *PUFS_DEVICE_HEALTH_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_DEVICE_HEALTH_DESCRIPTOR structure


## -description


The <b>UFS_DEVICE_HEALTH_DESCRIPTOR</b> structure describes the health of a device. 


## -struct-fields




### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorIDN

Specifies the descriptor's Identification value. <b>UFS_DEVICE_HEALTH_DESCRIPTOR </b>will have a value of <b>UFS_DESC_HEALTH_IDN</b>.


### -field bPreEOLInfo

Contains Pre-End of Life Information. This member supplies information about a device's life time as reflected by the average number of reserved blocks. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Member is not defined.</td>
</tr>
<tr>
<td>0x01</td>
<td>Normal. Consumed less than 80% of reserved blocks.</td>
</tr>
<tr>
<td>0x02</td>
<td>Consumed 80% of
reserved blocks.</td>
</tr>
<tr>
<td>0x03</td>
<td>Critical. Consumed 90% of
reserved blocks.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
 


### -field bDeviceLifeTimeEstA

<b>bDeviceLifeTimeEstA</b> provides an estimation of how much of a device's estimated life time has been used based on the amount of performed program/erase cycles. This calculation is vendor-specific and is referred as method A. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Information about device's life time not found.</td>
</tr>
<tr>
<td>0x01</td>
<td>0% to 10% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x02</td>
<td>10% to 20% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x03</td>
<td>20% to 30% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x04</td>
<td>30% to 40% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x05</td>
<td>40% to 50% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x06</td>
<td>50% to 60% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x07</td>
<td>60% to 70% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x08</td>
<td>70% to 80% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x09</td>
<td>80% to 90% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x0A</td>
<td>90% to 100% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x0B</td>
<td>Device has exceeded it's estimated life time.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
 


### -field bDeviceLifeTimeEstB

<b>bDeviceLifeTimeEstB</b> provides an estimation of how much of a device's estimated life time has been used based on the amount of performed program/erase cycles. This calculation is vendor-specific and is referred as method B. Contains the same possible values as <b>bDeviceLifeTimeEstA</b>.


### -field VendorPropInfo

 




#### - VendorPropInfo[32]

Reserved for vendor use.


## -remarks



The UFS Host Controller contains a series of configurable Descriptor Tables, which allow the driver to query and configure the host controller’s capabilities. Query the Requested Descriptor from the Descriptor Table on the device.



