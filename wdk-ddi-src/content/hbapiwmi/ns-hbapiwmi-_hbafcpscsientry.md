---
UID: NS:hbapiwmi._HBAFCPScsiEntry
title: "_HBAFCPScsiEntry"
author: windows-driver-content
description: The HBAFCPScsiEntry structure is used with GetFcpTargetMapping method of the MSFC_HBAFCPInfo WMI Class to define a binding between the operating system information that uniquely identifies a logical unit and the fibre channel protocol (FCP) identifier that identifies the logical unit.
old-location: storage\hbafcpscsientry.htm
tech.root: storage
ms.assetid: 718431f9-e4cc-4e79-84d3-a59f5399e711
ms.date: 03/29/2018
ms.keywords: "*PHBAFCPScsiEntry, HBAFCPScsiEntry, HBAFCPScsiEntry structure [Storage Devices], PHBAFCPScsiEntry, PHBAFCPScsiEntry structure pointer [Storage Devices], _HBAFCPScsiEntry, hbapiwmi/HBAFCPScsiEntry, hbapiwmi/PHBAFCPScsiEntry, storage.hbafcpscsientry, structs-Fibre_500172f1-a231-4530-afdf-fa0ba05d4904.xml"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	HBAFCPScsiEntry
product:
- Windows
targetos: Windows
req.typenames: HBAFCPScsiEntry, *PHBAFCPScsiEntry
---

# _HBAFCPScsiEntry structure


## -description


The HBAFCPScsiEntry structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a> to define a binding between the operating system information that uniquely identifies a logical unit and the fibre channel protocol (FCP) identifier that identifies the logical unit.  


## -struct-fields




### -field FCPId

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556038">HBAFCPID</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.


### -field Luid

Contains the logical unit descriptor for the device that the operating system derives from SCSI inquiry data. 


### -field ScsiId

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556042">HBAScsiID</a> that contains the information that uniquely identifies a logical unit for the operating system. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a>
 

 

