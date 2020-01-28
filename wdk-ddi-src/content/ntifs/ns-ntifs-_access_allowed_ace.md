---
UID: NS:ntifs._ACCESS_ALLOWED_ACE
title: _ACCESS_ALLOWED_ACE (ntifs.h)
description: The ACCESS_ALLOWED_ACE structure defines an access-control entry (ACE) for the discretionary access-control list (DACL) that controls access to an object.
old-location: ifsk\access_allowed_ace.htm
tech.root: ifsk
ms.assetid: 20373863-0850-4ccf-b94a-7d252ad15d20
ms.date: 04/16/2018
ms.keywords: "*PACCESS_ALLOWED_ACE, ACCESS_ALLOWED_ACE, ACCESS_ALLOWED_ACE structure [Installable File System Drivers], PACCESS_ALLOWED_ACE, PACCESS_ALLOWED_ACE structure pointer [Installable File System Drivers], _ACCESS_ALLOWED_ACE, ifsk.access_allowed_ace, ntifs/ACCESS_ALLOWED_ACE, ntifs/PACCESS_ALLOWED_ACE, securitystructures_2dd3ec4a-0dc9-4268-8968-1a284b7124e6.xml"
f1_keywords:
 - "ntifs/ACCESS_ALLOWED_ACE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- ACCESS_ALLOWED_ACE
product:
- Windows
targetos: Windows
req.typenames: ACCESS_ALLOWED_ACE
---

# _ACCESS_ALLOWED_ACE structure


## -description


The ACCESS_ALLOWED_ACE structure defines an access-control entry (ACE) for the discretionary access-control list (DACL) that controls access to an object. An access-allowed ACE allows access to an object for a specific subject identified by a security identifier (SID). 


## -struct-fields




### -field Header

Specifies an ACE_HEADER structure. 


### -field Mask

ACCESS_MASK structure that specifies the access rights granted by this ACE. 


### -field SidStart

Specifies a SID. The access rights specified by the <b>Mask</b> member are granted to any subject possessing an enabled SID matching this member. 


## -remarks



This structure must be aligned on a 32-bit boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_access_denied_ace">ACCESS_DENIED_ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_ace_header">ACE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtladdaccessallowedace">RtlAddAccessAllowedAce</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_system_alarm_ace">SYSTEM_ALARM_ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_system_audit_ace">SYSTEM_AUDIT_ACE</a>
 

 

