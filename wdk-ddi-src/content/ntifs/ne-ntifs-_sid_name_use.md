---
UID: NE:ntifs._SID_NAME_USE
title: "_SID_NAME_USE"
author: windows-driver-content
description: The SID_NAME_USE enumeration type contains values that specify the type of a security identifier (SID).
old-location: ifsk\sid_name_use.htm
old-project: ifsk
ms.assetid: c3dd02d1-c259-4c17-8bd5-ee304e576a39
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSID_NAME_USE, PSID_NAME_USE, PSID_NAME_USE enumeration pointer [Installable File System Drivers], SID_NAME_USE, SID_NAME_USE enumeration [Installable File System Drivers], SidTypeAlias, SidTypeComputer, SidTypeDeletedAccount, SidTypeDomain, SidTypeGroup, SidTypeInvalid, SidTypeLabel, SidTypeUnknown, SidTypeUser, SidTypeWellKnownGroup, _SID_NAME_USE, ifsk.sid_name_use, ntifs/PSID_NAME_USE, ntifs/SID_NAME_USE, ntifs/SidTypeAlias, ntifs/SidTypeComputer, ntifs/SidTypeDeletedAccount, ntifs/SidTypeDomain, ntifs/SidTypeGroup, ntifs/SidTypeInvalid, ntifs/SidTypeLabel, ntifs/SidTypeUnknown, ntifs/SidTypeUser, ntifs/SidTypeWellKnownGroup, securitystructures_7ff44465-6d8e-46f6-9bd4-b5be754dde4b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	SID_NAME_USE
product: Windows
targetos: Windows
req.typenames: SID_NAME_USE, *PSID_NAME_USE
---

# _SID_NAME_USE enumeration


## -description


The SID_NAME_USE enumeration type contains values that specify the type of a security identifier (SID).


## -enum-fields




### -field SidTypeUser

This value indicates a user SID.


### -field SidTypeGroup

This value indicates a group SID.


### -field SidTypeDomain

This value indicates a domain SID.


### -field SidTypeAlias

This value indicates an alias SID.


### -field SidTypeWellKnownGroup

This value indicates an SID for a well-known group.


### -field SidTypeDeletedAccount

This value indicates a SID for a deleted account.


### -field SidTypeInvalid

This value indicates an invalid SID.


### -field SidTypeUnknown

This value indicates an unknown SID type.


### -field SidTypeComputer

This value indicates a SID for a computer.


### -field SidTypeLabel


### -field SidTypeLogonSession




## -remarks



This enumeration type is the same as the Win32 SID_NAME_USE enumeration type defined in <i>winnt.h</i> used by the Win32 <b>LookupAccountName</b> and <b>LookupAccountSid</b> functions. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554795">SecLookupAccountName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556579">SecLookupAccountSid</a>
 

 

