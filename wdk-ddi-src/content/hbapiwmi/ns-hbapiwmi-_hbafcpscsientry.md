---
UID: NS:hbapiwmi._HBAFCPScsiEntry
title: _HBAFCPScsiEntry (hbapiwmi.h)
description: The HBAFCPScsiEntry structure is used with GetFcpTargetMapping method of the MSFC_HBAFCPInfo WMI Class to define a binding between the operating system information that uniquely identifies a logical unit and the fibre channel protocol (FCP) identifier that identifies the logical unit.
old-location: storage\hbafcpscsientry.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HBAFCPScsiEntry structure"]
ms.keywords: "*PHBAFCPScsiEntry, HBAFCPScsiEntry, HBAFCPScsiEntry structure [Storage Devices], PHBAFCPScsiEntry, PHBAFCPScsiEntry structure pointer [Storage Devices], _HBAFCPScsiEntry, hbapiwmi/HBAFCPScsiEntry, hbapiwmi/PHBAFCPScsiEntry, storage.hbafcpscsientry, structs-Fibre_500172f1-a231-4530-afdf-fa0ba05d4904.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
targetos: Windows
req.typenames: HBAFCPScsiEntry, *PHBAFCPScsiEntry
f1_keywords:
 - _HBAFCPScsiEntry
 - hbapiwmi/_HBAFCPScsiEntry
 - PHBAFCPScsiEntry
 - hbapiwmi/PHBAFCPScsiEntry
 - HBAFCPScsiEntry
 - hbapiwmi/HBAFCPScsiEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _HBAFCPScsiEntry
 - PHBAFCPScsiEntry
 - HBAFCPScsiEntry
---

# _HBAFCPScsiEntry structure


## -description

The HBAFCPScsiEntry structure is used with <a href="/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a> method of the <a href="/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a> to define a binding between the operating system information that uniquely identifies a logical unit and the fibre channel protocol (FCP) identifier that identifies the logical unit.

## -struct-fields

### -field FCPId

Contains a structure of type <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpid">HBAFCPID</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.

### -field Luid

Contains the logical unit descriptor for the device that the operating system derives from SCSI inquiry data.

### -field ScsiId

Contains a structure of type <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbascsiid">HBAScsiID</a> that contains the information that uniquely identifies a logical unit for the operating system.

## -see-also

<a href="/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a>

