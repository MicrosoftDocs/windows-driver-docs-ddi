---
UID: NS:ufs.__unnamed_struct_0
title: UFS_DEVICE_DESCRIPTOR (ufs.h)
description: UFS_DEVICE_DESCRIPTOR is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical units contained within the device.
old-location: storage\ufs_device_descriptor.htm
tech.root: storage
ms.assetid: CD1F59DA-3D84-422B-A862-8F4C5E1AA515
ms.date: 03/29/2018
ms.keywords: "*PUFS_DEVICE_DESCRIPTOR, PUFS_DEVICE_DESCRIPTOR, PUFS_DEVICE_DESCRIPTOR structure pointer [Storage Devices], UFS_DEVICE_DESCRIPTOR, UFS_DEVICE_DESCRIPTOR structure [Storage Devices], storage.ufs_device_descriptor, ufs/PUFS_DEVICE_DESCRIPTOR, ufs/UFS_DEVICE_DESCRIPTOR"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ufs.h
api_name:
-	UFS_DEVICE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: UFS_DEVICE_DESCRIPTOR, *PUFS_DEVICE_DESCRIPTOR
---

# UFS_DEVICE_DESCRIPTOR structure


## -description


<b>UFS_DEVICE_DESCRIPTOR</b> is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical
units contained within the device.


## -struct-fields




### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_DEVICE_IDN</b>.


### -field bDevice

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
 


### -field bDeviceClass

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
 


### -field bDeviceSubClass

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
 


### -field bProtocol

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
 


### -field bNumberLU

Specifies the number of Logical Units. This does not include the number of well known logical units.


### -field bNumberWLU

Specifies the number of well known logical units.


### -field bBootEnable

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
 


### -field bDescrAccessEn

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
 


### -field bInitPowerMode

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
 


### -field bHighPriorityLUN

<b>bHighPriorityLUN</b> defines the high priority
logical unit.


### -field bSecureRemovalType

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
 


### -field bSecurityLU

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
 


### -field bBackgroundOpsTermLat

<b>bBackgroundOpsTermLat</b> defines the maximum latency for starting data transmission when background
operations are ongoing. The termination latency limit applies to two cases:

<ul>
<li>When the device receives a COMMAND UFS Protocol Information Units (UPIU) with a transfer request. The device shall start the data
transfer and send a DATA IN UPIU or a RTT UPIU within the latency limit.</li>
<li>When the device receives QUERY REQUEST UPIU to clear the <b>fBackgroundOpsEn</b> Flag. The device is
expected to terminate background operations within the latency limit.</li>
</ul>

### -field bInitActiveICCLevel

<b>bInitActiveICCLevel</b> defines the <b>bActiveICCLevel</b>
value after power on or reset. The range of the value is from 0x00 to 0x0F. 


### -field wSpecVersion

Indicates the specification version in Binary Coded Decimal (BCD) format.


### -field wManufactureDate

Specifies the manufacturing date  in BCD format as 0xMMYY.


### -field iManufacturerName

Contains an index value to the string which contains the manufacturer's name.


### -field iProductName

Contains an index value to the string which contains the product's name.


### -field iSerialNumberID

Contains an index value to the string which contains the serial's number.


### -field iOemID

Contains an index value to the string which contains the OEM ID.


### -field wManufacturerID

Specifies the Manufacturer ID of the device.


### -field bUD0BaseOffset

Specifies the Offset of Unit Descriptor 0's configurable
parameters within the Configuration
Descriptor, <a href="https://msdn.microsoft.com/B65A2268-6959-4630-97DA-C0CFD37D9174">UFS_CONFIG_DESCRIPTOR</a>.


### -field bUDConfigPLength

Total size of a <b>UFS_UNIT_CONFIG_DESCRIPTOR</b>'s
parameters.


### -field bDeviceRTTCap

Specifies the maximum number of outstanding READY TO TRANSFER UPIU'S
supported by device. The minimum value is 2.


### -field wPeriodicRTCUpdate

Specifies the frequency and method of real-time clock updates. Bits 10 to 15 are reserved.


### -field bUFSFeaturesSupport

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
 


### -field bFFUTimeout

The maximum time, in seconds, that access
to the device is limited or not possible through
any ports associated due to execution of a
WRITE BUFFER command.


### -field bQueueDepth

Specifies the queue depth. If this member is equal to 0, the device implements the per-LU
queuing architecture.


### -field wDeviceVersion

Specifies the device version.


### -field bNumSecureWPArea

Specifies the total number of
Secure Write Protect Areas supported by the
device. The value of this member is between <b>bNumberLU</b> and 32


### -field dPSAMaxDataSize

Specifies the maximum
amount of data that may be written during the
pre-soldering phase of the PSA flow.


### -field dPSAStateTimeout

 


### -field iProductRevisionLevel

Specifies the index to the string which contains the Product
Revision Level.


### -field Reserved

Reserved for future use.


### -field Reserved2

Reserved for future use.


#### - bPSAStateTimeout

Specifies the command
maximum timeout for a change in <b>bPSAState</b>. The timeout value is calculated as follows (in microseconds):

100 x 2 ^ <b>bPSAStateTimeout</b>


## -remarks



If <b>bBootEnable</b> in the <b>UFS_DEVICE_DESCRIPTOR</b> is set to zero or if the Boot well known logical unit is not mapped to an enabled logical unit, then the Boot well known logical unit shall terminate.

<b>UFS_DEVICE_DESCRIPTOR</b> is read only, some of its parameters may be changed by changing the corresponding parameter in <a href="https://msdn.microsoft.com/09CBAD0A-CBDC-464E-908C-BF142D515969">UFS_UNIT_CONFIG_DESCRIPTOR</a>.




## -see-also




<a href="https://msdn.microsoft.com/B65A2268-6959-4630-97DA-C0CFD37D9174">UFS_CONFIG_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/6B085DBB-2AAA-4170-A2B1-EA4D2C207A24">UFS_DEVICE_HEALTH_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/DD3AEB66-E36B-4F18-AFEC-D344132D4B8C">UFS_GEOMETRY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/6C6EAA96-40E9-467F-903B-AE44CE5B77CF">UFS_INTERCONNECT_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/FCF9DCD1-2C04-47E3-97C5-7ACC28B28C6C">UFS_POWER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/19A066BD-1099-475C-BF81-F1BE7C7778E5">UFS_RPMB_UNIT_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/1F32DA95-6801-4C48-B3C4-A47C3E1C678B">UFS_STRING_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/09CBAD0A-CBDC-464E-908C-BF142D515969">UFS_UNIT_CONFIG_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/5D76C266-875A-40AC-9B26-F17978971783">UFS_UNIT_DESCRIPTOR</a>
 

 

