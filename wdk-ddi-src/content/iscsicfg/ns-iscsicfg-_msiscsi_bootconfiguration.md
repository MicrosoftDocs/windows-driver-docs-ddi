---
UID: NS:iscsicfg._MSiSCSI_BootConfiguration
title: "_MSiSCSI_BootConfiguration"
description: The MSiSCSI_BootConfiguration structure describes how the boot device is configured.
old-location: storage\msiscsi_bootconfiguration.htm
tech.root: storage
ms.assetid: 3a4b55b1-977d-43fb-9968-7a734e04b21b
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_BootConfiguration, MSiSCSI_BootConfiguration, MSiSCSI_BootConfiguration structure [Storage Devices], PMSiSCSI_BootConfiguration, PMSiSCSI_BootConfiguration structure pointer [Storage Devices], _MSiSCSI_BootConfiguration, iscsicfg/MSiSCSI_BootConfiguration, iscsicfg/PMSiSCSI_BootConfiguration, storage.msiscsi_bootconfiguration, structs-iSCSI_eb9ca716-5f5e-4bec-a4e0-e00d5a93b329.xml"
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
-	MSiSCSI_BootConfiguration
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_BootConfiguration, *PMSiSCSI_BootConfiguration
---

# _MSiSCSI_BootConfiguration structure


## -description


The MSiSCSI_BootConfiguration structure describes how the boot device is configured. 


## -struct-fields




### -field LUN

The logical unit number (LUN) that identifies the logical unit on the target that functions as a boot device.


### -field SecurityFlags

A bitwise OR of security flags that indicate the security requirements of the boot device. For a list of possible flags for this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>.


### -field UsernameSize

The size, in bytes, of the string in <b>Username</b>.


### -field PasswordSize

The size, in bytes, of the string in <b>Password</b>.


### -field DiscoverBootDevice

A Boolean value that indicates whether the system should dynamically discover the boot device. If this member is <b>TRUE</b>, the system should dynamically discover the boot device. 


### -field InitiatorNode

The iSCSI name of the initiator node to use for connecting to the boot device. If this member is <b>NULL</b>, the HBA can choose any initiator node. The iSCSI name for the initiator uniquely identifies the initiator anywhere in the world. For more information about how to specify this name, see the <i>iSCSI </i>specification that is published by the Internet Engineering Task Force (IETF) of the IP storage working group. 


### -field TargetName

The iSCSI name for the target that contains the boot device.


### -field TargetPortal

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561574">ISCSI_TargetPortal</a> structure that specifies the portal to use for the connection.


### -field LoginOptions

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561541">ISCSI_LoginOptions</a> structure that specifies the characteristics of the logon session to establish with the boot device.


### -field Username

A variable length array of characters that specifies the user name to use with the challenge handshake authentication protocol (CHAP). The user name is also known as the <i>CHAP name</i> (CHAP_N). The initiator uses the CHAP name to authenticate the target.


## -remarks



The WMI tool suite automatically generates a declaration of the MSiSCSI_BootConfiguration structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562979">MSiSCSI_BootConfiguration WMI Class</a> in <i>Config.mof</i>.It is optional that you implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561541">ISCSI_LoginOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561574">ISCSI_TargetPortal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562979">MSiSCSI_BootConfiguration WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>
 

 

