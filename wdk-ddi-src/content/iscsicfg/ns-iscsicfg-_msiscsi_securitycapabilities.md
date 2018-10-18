---
UID: NS:iscsicfg._MSiSCSI_SecurityCapabilities
title: "_MSiSCSI_SecurityCapabilities"
author: windows-driver-content
description: The MSiSCSI_SecurityCapabilities structure describes the security capabilities of an initiator.
old-location: storage\msiscsi_securitycapabilities.htm
tech.root: storage
ms.assetid: a385283a-7b24-43aa-b291-541bfd6a91a6
ms.date: 3/29/2018
ms.keywords: "*PMSiSCSI_SecurityCapabilities, MSiSCSI_SecurityCapabilities, MSiSCSI_SecurityCapabilities structure [Storage Devices], PMSiSCSI_SecurityCapabilities, PMSiSCSI_SecurityCapabilities structure pointer [Storage Devices], _MSiSCSI_SecurityCapabilities, iscsicfg/MSiSCSI_SecurityCapabilities, iscsicfg/PMSiSCSI_SecurityCapabilities, storage.msiscsi_securitycapabilities, structs-iSCSI_0e8b2bb9-69df-4d36-8002-ac32177b724a.xml"
ms.topic: struct
req.header: iscsicfg.h
req.include-header: Iscsicfg.h
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
-	iscsicfg.h
api_name:
-	MSiSCSI_SecurityCapabilities
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_SecurityCapabilities, *PMSiSCSI_SecurityCapabilities
---

# _MSiSCSI_SecurityCapabilities structure


## -description


The MSiSCSI_SecurityCapabilities structure describes the security capabilities of an initiator. 


## -struct-fields




### -field ProtectiScsiTraffic

A Boolean value that indicates whether the initiator can use IPsec to protect iSCSI traffic. If this member is <b>TRUE</b>, the initiator can use IPsec to protect iSCSI traffic. If <b>FALSE</b>, the initiator cannot use IPsec.


### -field ProtectiSNSTraffic

A Boolean value that indicates whether the initiator can use IPsec to protect iSNS traffic. If this member is <b>TRUE</b>, the initiator can use IPsec to protect iSNS traffic. If <b>FALSE</b>, the initiator cannot use IPsec.


### -field CertificatesSupported

A Boolean value that indicates whether the initiator supports certificates. If this member is <b>TRUE</b>, the initiator supports certificates. If this member is <b>FALSE</b>, the initiatiator does not support certificates.


### -field EncryptionAvailableCount

The number of encryption types that the initiator supports. 


### -field EncryptionAvailable

A variable length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561528">ISCSI_ENCRYPTION_TYPES</a> structures, which indicate types of encryption that the initiator supports. 


## -remarks



The WMI tool suite automatically generates a declaration of the MSiSCSI_SecurityCapabilities structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563131">MSiSCSI_SecurityCapabilities WMI Class</a> in <i>Config.mof</i>. 

Initiators that support IPsec must implement the MSiSCSI_SecurityCapabilities class. 

Initiators must register the MSiSCSI_SecurityCapabilities class using the name of the physical device object (PDO) for the HBA. You must implement this class if the adapter supports IPsec.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561528">ISCSI_ENCRYPTION_TYPES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563131">MSiSCSI_SecurityCapabilities WMI Class</a>
 

 

