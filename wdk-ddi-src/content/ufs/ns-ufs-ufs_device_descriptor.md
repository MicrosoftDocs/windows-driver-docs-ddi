---
UID: NS:ufs.UFS_DEVICE_DESCRIPTOR
title: UFS_DEVICE_DESCRIPTOR
author: windows-driver-content
description: UFS_DEVICE_DESCRIPTOR is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical units contained within the device.
old-location: storage\ufs_device_descriptor.htm
old-project: storage
ms.assetid: CD1F59DA-3D84-422B-A862-8F4C5E1AA515
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PUFS_DEVICE_DESCRIPTOR, storage.ufs_device_descriptor, ufs/UFS_DEVICE_DESCRIPTOR, UFS_DEVICE_DESCRIPTOR, PUFS_DEVICE_DESCRIPTOR structure pointer [Storage Devices], UFS_DEVICE_DESCRIPTOR structure [Storage Devices], PUFS_DEVICE_DESCRIPTOR, ufs/PUFS_DEVICE_DESCRIPTOR"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ufs.h
apiname:
-	UFS_DEVICE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_DEVICE_DESCRIPTOR, *PUFS_DEVICE_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_DEVICE_DESCRIPTOR structure


## -description


<b>UFS_DEVICE_DESCRIPTOR</b> is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical
units contained within the device.


## -syntax


````
typedef struct _UFS_DEVICE_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorIDN;
  UCHAR bDevice;
  UCHAR bDeviceClass;
  UCHAR bDeviceSubClass;
  UCHAR bProtocol;
  UCHAR  bNumberLU;
  UCHAR bNumberWLU;
  UCHAR bBootEnable;
  UCHAR bDescrAccessEn;
  UCHAR bInitPowerMode;
  UCHAR bHighPriorityLUN;
  UCHAR bSecureRemovalType;
  UCHAR bSecurityLU;
  UCHAR bBackgroundOpsTermLat;
  UCHAR bInitActiveICCLevel;
  UCHAR wSpecVersion[2];
  UCHAR wManufactureDate[2];
  UCHAR iManufacturerName;
  UCHAR iProductName;
  UCHAR iSerialNumberID;
  UCHAR iOemID;
  UCHAR wManufacturerID[2];
  UCHAR bUD0BaseOffset;
  UCHAR bUDConfigPLength;
  UCHAR bDeviceRTTCap;
  UCHAR wPeriodicRTCUpdate[2];
  UCHAR bUFSFeaturesSupport;
  UCHAR bFFUTimeout;
  UCHAR bQueueDepth;
  UCHAR wDeviceVersion[2];
  UCHAR bNumSecureWPArea;
  UCHAR dPSAMaxDataSize[4];
  UCHAR bPSAStateTimeout;
  UCHAR  iProductRevisionLevel;
  UCHAR Reserved[5];
  UCHAR Reserved2[16];
} UFS_DEVICE_DESCRIPTOR, *PUFS_DEVICE_DESCRIPTOR;
````


## -struct-fields




#### - bLength

Specifies the length, in bytes, of this descriptor.


#### - bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_DEVICE_IDN</b>.


#### - bDevice

Specifies the device type.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Device</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bDeviceClass

Specifies the device class.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Mass Storage</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bDeviceSubClass

Specifies the UFS mass storage subclasses in a bit map as follows:
<table>
<tr>
<th>Bit</th>
<th>Value</th>
</tr>
<tr>
<td>0</td>
<td>Bootable / Non-Bootable</td>
</tr>
<tr>
<td>1</td>
<td>Embedded / Removable</td>
</tr>
<tr>
<td>2</td>
<td>Reserved for JESD220-1 (UME)</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bProtocol

Specifies the protocol support by the UFS device.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>SCSI</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bNumberLU

Specifies the number of Logical Units. This does not include the number of well known logical units.


#### - bNumberWLU

Specifies the number of well known logical units.


#### - bBootEnable

Specifies if a device's boot feature is enabled.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Boot feature disabled</td>
</tr>
<tr>
<td>0x01</td>
<td>Boot feature enabled</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bDescrAccessEn

Indicates whether the Device Descriptor can be
read after the partial initialization phase of the
boot sequence.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Device Descriptor access disabled</td>
</tr>
<tr>
<td>0x01</td>
<td>Device Descriptor access enabled</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bInitPowerMode

<b>bInitPowerMode</b> defines the Power Mode
after device initialization or hardware reset.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>UFS-Sleep mode</td>
</tr>
<tr>
<td>0x01</td>
<td>Active-mode</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bHighPriorityLUN

<b>bHighPriorityLUN</b> defines the high priority
logical unit.


#### - bSecureRemovalType

Specifies the secure removal type.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Information removed by an erase of the
physical memory</td>
</tr>
<tr>
<td>0x01</td>
<td>Information removed by overwriting the
addressed locations with a single character
followed by an erase.</td>
</tr>
<tr>
<td>0x02</td>
<td>Information removed by overwriting the
addressed locations with a character, its
complement, then a random character.</td>
</tr>
<tr>
<td>0x03</td>
<td>Information removed using a vendor
define mechanism.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bSecurityLU

Specifies if there is support for security LU's
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Not supported</td>
</tr>
<tr>
<td>0x01</td>
<td>Replay Protected Memory Block (RPMB)</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bBackgroundOpsTermLat

<b>bBackgroundOpsTermLat</b> defines the maximum latency for starting data transmission when background
operations are ongoing. The termination latency limit applies to two cases:
<ul>
<li>When the device receives a COMMAND UFS Protocol Information Units (UPIU) with a transfer request. The device shall start the data
transfer and send a DATA IN UPIU or a RTT UPIU within the latency limit.</li>
<li>When the device receives QUERY REQUEST UPIU to clear the <b>fBackgroundOpsEn</b> Flag. The device is
expected to terminate background operations within the latency limit.</li>
</ul>

#### - bInitActiveICCLevel

<b>bInitActiveICCLevel</b> defines the <b>bActiveICCLevel</b>
value after power on or reset. The range of the value is from 0x00 to 0x0F. 


#### - wSpecVersion

Indicates the specification version in Binary Coded Decimal (BCD) format.


#### - wManufactureDate

Specifies the manufacturing date  in BCD format as 0xMMYY.


#### - iManufacturerName

Contains an index value to the string which contains the manufacturer's name.


#### - iProductName

Contains an index value to the string which contains the product's name.


#### - iSerialNumberID

Contains an index value to the string which contains the serial's number.


#### - iOemID

Contains an index value to the string which contains the OEM ID.


#### - wManufacturerID

Specifies the Manufacturer ID of the device.


#### - bUD0BaseOffset

Specifies the Offset of Unit Descriptor 0's configurable
parameters within the Configuration
Descriptor, <a href="..\ufs\ns-ufs-ufs_config_descriptor.md">UFS_CONFIG_DESCRIPTOR</a>.


#### - bUDConfigPLength

Total size of a <b>UFS_UNIT_CONFIG_DESCRIPTOR</b>'s
parameters.


#### - bDeviceRTTCap

Specifies the maximum number of outstanding READY TO TRANSFER UPIU'S
supported by device. The minimum value is 2.


#### - wPeriodicRTCUpdate

Specifies the frequency and method of real-time clock updates. Bits 10 to 15 are reserved.


#### - bUFSFeaturesSupport

Specifies which features are supported on this device. A feature is supported if its related bit is set to 1.
<table>
<tr>
<th>Bit</th>
<th>Value</th>
</tr>
<tr>
<td>0</td>
<td>Field Firmware Update (FFU)</td>
</tr>
<tr>
<td>1</td>
<td>Production State Awarness (PSA)</td>
</tr>
<tr>
<td>2</td>
<td>Device Life Span</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table> 


#### - bFFUTimeout

The maximum time, in seconds, that access
to the device is limited or not possible through
any ports associated due to execution of a
WRITE BUFFER command.


#### - bQueueDepth

Specifies the queue depth. If this member is equal to 0, the device implements the per-LU
queuing architecture.


#### - wDeviceVersion

Specifies the device version.


#### - bNumSecureWPArea

Specifies the total number of
Secure Write Protect Areas supported by the
device. The value of this member is between <b>bNumberLU</b> and 32


#### - dPSAMaxDataSize

Specifies the maximum
amount of data that may be written during the
pre-soldering phase of the PSA flow.


### -field dPSAStateTimeout

 


#### - iProductRevisionLevel

Specifies the index to the string which contains the Product
Revision Level.


#### - Reserved

Reserved for future use.


#### - Reserved2

Reserved for future use.


#### - bPSAStateTimeout

Specifies the command
maximum timeout for a change in <b>bPSAState</b>. The timeout value is calculated as follows (in microseconds):

100 x 2 ^ <b>bPSAStateTimeout</b>


## -remarks


If <b>bBootEnable</b> in the <b>UFS_DEVICE_DESCRIPTOR</b> is set to zero or if the Boot well known logical unit is not mapped to an enabled logical unit, then the Boot well known logical unit shall terminate.

<b>UFS_DEVICE_DESCRIPTOR</b> is read only, some of its parameters may be changed by changing the corresponding parameter in <a href="..\ufs\ns-ufs-ufs_unit_config_descriptor.md">UFS_UNIT_CONFIG_DESCRIPTOR</a>.



## -see-also

<a href="..\ufs\ns-ufs-ufs_config_descriptor.md">UFS_CONFIG_DESCRIPTOR</a>

<a href="..\ufs\ns-ufs-ufs_unit_descriptor.md">UFS_UNIT_DESCRIPTOR</a>

<a href="..\ufs\ns-ufs-_ufs_string_descriptor.md">UFS_STRING_DESCRIPTOR</a>

<a href="..\ufs\ns-ufs-ufs_unit_config_descriptor.md">UFS_UNIT_CONFIG_DESCRIPTOR</a>

<a href="..\ufs\ns-ufs-ufs_geometry_descriptor.md">UFS_GEOMETRY_DESCRIPTOR</a>

<a href="..\ufs\ns-ufs-ufs_rpmb_unit_descriptor.md">UFS_RPMB_UNIT_DESCRIPTOR</a>

<a href="..\ufs\ns-ufs-ufs_device_health_descriptor.md">UFS_DEVICE_HEALTH_DESCRIPTOR</a>

<a href="..\ufs\ns-ufs-ufs_power_descriptor.md">UFS_POWER_DESCRIPTOR</a>

<a href="..\ufs\ns-ufs-ufs_interconnect_descriptor.md">UFS_INTERCONNECT_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20UFS_DEVICE_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

