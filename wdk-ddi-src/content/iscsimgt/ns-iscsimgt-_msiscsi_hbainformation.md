---
UID: NS:iscsimgt._MSiSCSI_HBAInformation
title: "_MSiSCSI_HBAInformation"
author: windows-driver-content
description: The MSiSCSI_HBAInformation structure is used by storage miniport drivers to report information about the host bus adapters (HBAs) that they manage to the iSCSI initiator service.
old-location: storage\msiscsi_hbainformation.htm
old-project: storage
ms.assetid: ee2951e0-2632-44b0-870d-33d4d48ac8e8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSiSCSI_HBAInformation, MSiSCSI_HBAInformation, MSiSCSI_HBAInformation structure [Storage Devices], PMSiSCSI_HBAInformation, PMSiSCSI_HBAInformation structure pointer [Storage Devices], _MSiSCSI_HBAInformation, iscsimgt/MSiSCSI_HBAInformation, iscsimgt/PMSiSCSI_HBAInformation, storage.msiscsi_hbainformation, structs-iSCSI_f6de2645-3ba4-444e-97a8-3115eb109a95.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	iscsimgt.h
api_name:
-	MSiSCSI_HBAInformation
product: Windows
targetos: Windows
req.typenames: MSiSCSI_HBAInformation, *PMSiSCSI_HBAInformation
---

# _MSiSCSI_HBAInformation structure


## -description


The MSiSCSI_HBAInformation structure is used by storage miniport drivers to report information about the host bus adapters (HBAs) that they manage to the iSCSI initiator service.


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). 


### -field IntegratedTCPIP

A Boolean value that indicates if the Windows TCP/IP stack manages TCP/IP traffic for the HBA. If this member is <b>TRUE</b>, the Windows TCP/IP stack manages TCP/IP traffic for the HBA. If this member is <b>FALSE</b>, the Windows TCP/IP stack does not manage TCP/IP traffic for the HBA. A miniport driver for an adapter with its own TCP/IP stack should set this member to <b>FALSE</b>.


### -field RequiresBinaryIpAddresses

A Boolean value that indicates whether the miniport driver for the HBA instructs the iSCSI initiator service to perform DNS lookup and provide the HBA with binary IP addresses. If this member is <b>TRUE</b>, the miniport driver for the HBA instructs the iSCSI initiator service to perform DNS lookup and provide the HBA with binary IP addresses. For the iSCSI initiator service to honor this request, the HBA must be on the same network as the Windows TCP/IP stack. If <b>RequiresBinaryIpAddresses</b> is <b>FALSE</b>, the HBA and its miniport driver have direct access to DNS. 


### -field VersionMin

The earliest version of the iSCSI specification that the HBA and its miniport driver support. 


### -field VersionMax

The most recent version of the iSCSI specification that the HBA and its miniport driver support. 


### -field MultifunctionDevice

A Boolean value that indicates whether the HBA is a multifunction device. If this member is <b>TRUE</b>, the HBA is a multifunction device, and it exposes a netcard interface. If this member <b>FALSE</b>, the HBA is not a multifunction device.


### -field CacheValid

A Boolean value that indicates if the adapter caches are value. If this member is <b>TRUE</b>, the adapter caches are valid. If this member is <b>FALSE</b>, the caches are invalid or the adapter does not cache data. 


### -field NumberOfPorts

The number of ports (or TCP/IP addresses on the adapter).


### -field Status

The current status of HBA. This member can hold any of the following values:

<table>
<tr>
<th>Status</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ISCSI_HBA_STATUS_WORKING

</td>
<td>
The HBA is functioning normally. 

</td>
</tr>
<tr>
<td>
ISCSI_HBA_STATUS_DEGRADED

</td>
<td>
The HBA is functioning in a degraded state of operation.

</td>
</tr>
<tr>
<td>
ISCSI_HBA_STATUS_CRITICAL

</td>
<td>
The HBA is in a critical state and might fail at any moment.

</td>
</tr>
<tr>
<td>
ISCSI_HBA_STATUS_FAILED

</td>
<td>
The HBA is not functioning at all.

</td>
</tr>
</table>
 


### -field FunctionalitySupported

A bitwise OR of the flags that define the functionality that the HBA supports. The following table describes the possible flags.

<table>
<tr>
<th>Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ISCSI_HBA_PRESHARED_KEY_CACHE

</td>
<td>
The host bus adapter (HBA) supports an onboard cache for a preshared key.

</td>
</tr>
<tr>
<td>
ISCSI_HBA_ISCSI_AUTHENTICATION_CACHE

</td>
<td>
The HBA supports an onboard cache for CHAP secrets. 

</td>
</tr>
<tr>
<td>
ISCSI_HBA_IPSEC_TUNNEL_MODE

</td>
<td>
The HBA supports IPsec tunnel mode. 

</td>
</tr>
<tr>
<td>
ISCSI_HBA_CHAP_VIA_RADIUS

</td>
<td>
The HBA supports the Remote Authentication Dial-In User Service (RADIUS) attributes of the challenge handshake authentication protocol (CHAP).

</td>
</tr>
<tr>
<td>
ISCSI_HBA_ISNS_DISCOVERY

</td>
<td>
The HBA supports iSNS discovery.

</td>
</tr>
<tr>
<td>
ISCSI_HBA_SLP_DISCOVERY

</td>
<td>
The HBA supports SLP discovery. 

</td>
</tr>
</table>
 


### -field GenerationalGuid

The generational GUID. This GUID is the GUID value that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565678">SetGenerationalGuid</a> method in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a> last set.


### -field MaxCDBLength

The maximum CDB length, in bytes, that the HBA supports.


### -field BiDiScsiCommands

A Boolean value that indicates if the HBA supports bidirectional SCSI commands. If this member is <b>TRUE</b>, the HBA supports bidirectional SCSI commands. If this member is <b>FALSE</b>, the HBA does not support bidirectional commands.


### -field VendorID

The manufacturer of the HBA.


### -field VendorModel

A string that specifies the model of the HBA. The manufacturer defines this string.


### -field VendorVersion

A string that specifies the version of the HBA. The manufacturer defines this string.


### -field FirmwareVersion

A string that specifies the version of the firmware in the HBA. The manufacturer defines this string.


### -field AsicVersion

A string that specifies the Asic version. The manufacturer defines this string.


### -field OptionRomVersion

A string that specifies the option ROM version of the HBA. The manufacturer defines this string.


### -field SerialNumber

A string that specifies the serial number of the HBA. The manufacturer defines this string.


### -field DriverName

A string that specifies the name of the driver for the HBA.


## -remarks



You must implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563017">MSiSCSI_HBAInformation WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565678">SetGenerationalGuid</a>
 

 

