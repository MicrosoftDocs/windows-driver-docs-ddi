---
UID: NS:hbapiwmi._HBAFCPScsiEntry
title: "_HBAFCPScsiEntry"
author: windows-driver-content
description: The HBAFCPScsiEntry structure is used with GetFcpTargetMapping method of the MSFC_HBAFCPInfo WMI Class to define a binding between the operating system information that uniquely identifies a logical unit and the fibre channel protocol (FCP) identifier that identifies the logical unit.
old-location: storage\hbafcpscsientry.htm
old-project: storage
ms.assetid: 718431f9-e4cc-4e79-84d3-a59f5399e711
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBAFCPScsiEntry structure [Storage Devices], HBAFCPScsiEntry, storage.hbafcpscsientry, PHBAFCPScsiEntry, *PHBAFCPScsiEntry, _HBAFCPScsiEntry, hbapiwmi/HBAFCPScsiEntry, hbapiwmi/PHBAFCPScsiEntry, structs-Fibre_500172f1-a231-4530-afdf-fa0ba05d4904.xml, PHBAFCPScsiEntry structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	HBAFCPScsiEntry
product: Windows
targetos: Windows
req.typenames: HBAFCPScsiEntry, *PHBAFCPScsiEntry
---

# _HBAFCPScsiEntry structure


## -description


The HBAFCPScsiEntry structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a> to define a binding between the operating system information that uniquely identifies a logical unit and the fibre channel protocol (FCP) identifier that identifies the logical unit.  


## -syntax


````
typedef struct _HBAFCPScsiEntry {
  HBAFCPID  FCPId;
  UCHAR     Luid[256];
  HBAScsiID ScsiId;
} HBAFCPScsiEntry, *PHBAFCPScsiEntry;
````


## -struct-fields




### -field FCPId

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpid.md">HBAFCPID</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.


### -field Luid

Contains the logical unit descriptor for the device that the operating system derives from SCSI inquiry data. 


### -field ScsiId

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbascsiid.md">HBAScsiID</a> that contains the information that uniquely identifies a logical unit for the operating system. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBAFCPScsiEntry structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

