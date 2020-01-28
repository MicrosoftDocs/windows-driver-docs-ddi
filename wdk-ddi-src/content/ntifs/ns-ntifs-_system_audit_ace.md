---
UID: NS:ntifs._SYSTEM_AUDIT_ACE
title: _SYSTEM_AUDIT_ACE (ntifs.h)
description: The SYSTEM_AUDIT_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying what types of access cause system-level notifications.
old-location: ifsk\system_audit_ace.htm
tech.root: ifsk
ms.assetid: 03806d36-0066-4603-ba53-10149778b4e7
ms.date: 04/16/2018
ms.keywords: "*PSYSTEM_AUDIT_ACE, PSYSTEM_AUDIT_ACE, PSYSTEM_AUDIT_ACE structure pointer [Installable File System Drivers], SYSTEM_AUDIT_ACE, SYSTEM_AUDIT_ACE structure [Installable File System Drivers], _SYSTEM_AUDIT_ACE, ifsk.system_audit_ace, ntifs/PSYSTEM_AUDIT_ACE, ntifs/SYSTEM_AUDIT_ACE, securitystructures_f47f7528-0214-4efc-9ec8-0f799d643299.xml"
f1_keywords:
 - "ntifs/SYSTEM_AUDIT_ACE"
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
- SYSTEM_AUDIT_ACE
product:
- Windows
targetos: Windows
req.typenames: SYSTEM_AUDIT_ACE
---

# _SYSTEM_AUDIT_ACE structure


## -description


The SYSTEM_AUDIT_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying what types of access cause system-level notifications. A system-audit ACE causes an audit message to be logged when a specified user or group attempts to gain access to an object. The user or group is identified by a security identifier (SID). 


## -struct-fields




### -field Header

Specifies an ACE_HEADER structure. 


### -field Mask

Specifies an ACCESS_MASK structure that gives the access rights causing audit messages to be generated. The SUCCESSFUL_ACCESS_ACE_FLAG and FAILED_ACCESS_ACE_FLAG flags in the <b>AceFlags</b> member of the ACE_HEADER structure indicate whether messages are generated for successful access attempts, unsuccessful access attempts, or both. 


### -field SidStart

Specifies a SID. An access attempt of a kind specified by the <b>Mask</b> member by any user or group whose SID matches the <b>SidStart</b> member causes the system to generate an audit message. If an application does not specify a SID for this member, audit messages are generated for the specified access rights for all users and groups. 


## -remarks



Audit messages are stored in an event log that can be manipulated by using the Microsoft Win32 event-logging functions or by using the Event Viewer (EVENTVWR.EXE). 

This structure must be aligned on a 32-bit boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_access_allowed_ace">ACCESS_ALLOWED_ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_access_denied_ace">ACCESS_DENIED_ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_ace_header">ACE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_system_alarm_ace">SYSTEM_ALARM_ACE</a>
 

 

