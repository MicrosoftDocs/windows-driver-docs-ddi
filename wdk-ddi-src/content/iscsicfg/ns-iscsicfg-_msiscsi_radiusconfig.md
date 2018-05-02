---
UID: NS:iscsicfg._MSiSCSI_RADIUSConfig
title: "_MSiSCSI_RADIUSConfig"
author: windows-driver-content
description: The MSiSCSI_RADIUSConfig structure provides information that the initiator requires to use the remote authentication dial-in user service (RADIUS).
old-location: storage\msiscsi_radiusconfig.htm
old-project: storage
ms.assetid: 6f8be86e-2729-4aa9-982d-df323f05cf1c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSiSCSI_RADIUSConfig, MSiSCSI_RADIUSConfig, MSiSCSI_RADIUSConfig structure [Storage Devices], PMSiSCSI_RADIUSConfig, PMSiSCSI_RADIUSConfig structure pointer [Storage Devices], _MSiSCSI_RADIUSConfig, iscsicfg/MSiSCSI_RADIUSConfig, iscsicfg/PMSiSCSI_RADIUSConfig, storage.msiscsi_radiusconfig, structs-iSCSI_9f8461c3-b370-4aed-a5a5-58f9dd276944.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	MSiSCSI_RADIUSConfig
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_RADIUSConfig, *PMSiSCSI_RADIUSConfig
---

# _MSiSCSI_RADIUSConfig structure


## -description


The MSiSCSI_RADIUSConfig structure provides information that the initiator requires to use the remote authentication dial-in user service (RADIUS).


## -struct-fields




### -field UseRADIUSForCHAP

A Boolean value that indicates whether the initiator should use RADIUS for authentication during the challenge handshake of the challenge handshake authentication protocol (CHAP). If this member is <b>TRUE</b>, the initiator should use RADIUS for authentication during the challenge handshake of CHAP. If this member is <b>FALSE</b>, the initiator is not required to use RADIUS.


### -field SharedSecretSizeInBytes

The size, in bytes, of shared secret for use with RADIUS servers.


### -field RADIUSServer

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a> structure that specifies a fixed address for the RADIUS server. The ISCSI_IP_Address structure defines the IP address in a way that is independent of the version of the IP protocol in use. 


### -field BackupRADIUSServer

A ISCSI_IP_Address structure that specifies a fixed addresses for a backup RADIUS server. 


### -field Reserved

Reserved for Microsoft use only. Set this member to zero.


### -field SharedSecret

A variable-length array that contains a shared secret. The initiator uses this shared secret to authenticate primary and backup RADIUS servers.


## -remarks



Initiators use RADIUS servers to perform authentication during the challenge handshake of CHAP.

The WMI tool suite automatically generates a declaration of the MSiSCSI_RADIUSConfig structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563114">MSiSCSI_RADIUSConfig WMI Class</a> in <i>Config.mof</i>. 

Initiators that support using RADIUS for CHAP authentication must implement the MSiSCSI_RADIUSConfig class.

Initiators should use RADIUS whenever possible, because RADIUS allows the centralized management of CHAP credentials. 

Initiators should register each instance of the MSiSCSI_RADIUSConfig class using the name of the physical device object (PDO) for the HBAYou must implement this class if the adapter supports authentication via RADIUS.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563114">MSiSCSI_RADIUSConfig WMI Class</a>
 

 

