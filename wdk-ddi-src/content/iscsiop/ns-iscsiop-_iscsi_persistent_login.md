---
UID: NS:iscsiop._ISCSI_Persistent_Login
title: "_ISCSI_Persistent_Login"
author: windows-driver-content
description: The ISCSI_Persistent_Login structure defines a persistent logon that the operating system initiates automatically when the computer boots up.
old-location: storage\iscsi_persistent_login.htm
old-project: storage
ms.assetid: c43ee3dd-552a-41ab-9b4f-01611e44f453
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PISCSI_Persistent_Login, ISCSI_Persistent_Login, ISCSI_Persistent_Login structure [Storage Devices], PISCSI_Persistent_Login, PISCSI_Persistent_Login structure pointer [Storage Devices], _ISCSI_Persistent_Login, iscsiop/ISCSI_Persistent_Login, iscsiop/PISCSI_Persistent_Login, storage.iscsi_persistent_login, structs-iSCSI_86b54cb5-df75-47c0-8dc4-337a5f46bea0.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
api_name:
-	ISCSI_Persistent_Login
product: Windows
targetos: Windows
req.typenames: ISCSI_Persistent_Login, *PISCSI_Persistent_Login
---

# _ISCSI_Persistent_Login structure


## -description


The ISCSI_Persistent_Login structure defines a persistent logon that the operating system initiates automatically when the computer boots up.


## -struct-fields




### -field TargetName

A wide character string that indicates the name of the target with which the iSCSI initiator service establishes a persistent logon when it restarts.


### -field SecurityFlags

A bitwise OR of security flags that indicate the security requirements of the target that is specified in the persistent logon. For a list of possible values for this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>.


### -field InitiatorPortNumber

The port number on the initiator side to perform the logon operation through. 


### -field UsernameSize

The size, in bytes, of the string in <b>Username</b>.


### -field IsInformationalSession

A Boolean value that indicates whether the persistent logon is configured to establish a purely informational session. If this member is <b>TRUE</b>, the persistent logon is configured to establish a purely informational session.


### -field UniqueIdForISID

Portal to use for initial connection


### -field TargetPortal

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff561574">ISCSI_TargetPortal</a> structure that specifies which target portal to use for the initial logon connection.


### -field LoginOptions

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff561541">ISCSI_LoginOptions</a> structure that specifies the characteristics of the persistent logon session. 


### -field TargetMapping

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff561572">ISCSI_TargetMapping</a> structure that defines the target mappings. 


### -field Username

A variable-length array of characters that specifies the challenge handshake authentication protocol user name (CHAP_N) to use when the initiator is authenticating the target. The number of elements in the array is specified by the <b>UsernameSize</b> field.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561541">ISCSI_LoginOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561556">ISCSI_Persistent_Login WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561572">ISCSI_TargetMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561574">ISCSI_TargetPortal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_Persistent_Login structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

