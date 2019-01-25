---
UID: NS:wdm._ACCESS_STATE
title: "_ACCESS_STATE" (wdm.h)
description: The ACCESS_STATE structure describes the state of an access in progress.
old-location: ifsk\access_state.htm
tech.root: ifsk
ms.assetid: 3d1d6407-f853-48d5-bd54-2eacece48b84
ms.date: 04/16/2018
ms.keywords: "*PACCESS_STATE, ACCESS_STATE, ACCESS_STATE structure [Installable File System Drivers], PACCESS_STATE, PACCESS_STATE structure pointer [Installable File System Drivers], _ACCESS_STATE, ifsk.access_state, securitystructures_41c08d1c-9d46-4df7-a1fe-dc274e8b3fe7.xml, wdm/ACCESS_STATE, wdm/PACCESS_STATE"
ms.topic: struct
req.header: wdm.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	ACCESS_STATE
product:
- Windows
targetos: Windows
req.typenames: ACCESS_STATE, *PACCESS_STATE
---

# _ACCESS_STATE structure


## -description


The ACCESS_STATE structure describes the state of an access in progress. It contains an object's subject context, remaining desired access types, granted access types, and, optionally, a privilege set to indicate which privileges were used to permit the access. 

Drivers are not to modify the ACCESS_STATE structure directly. To create and manipulate this structure, use the support routines listed in the See Also section. 


## -struct-fields




### -field OperationID

The identifier of the operation that this access relates to. This member is replaced by TransactionId in the <b>AuxData</b> member and is currently unused by drivers. 


### -field SecurityEvaluated

A Boolean value that specifies whether security was evaluated as part of the access check. This member is currently unused by drivers. 


### -field GenerateAudit

A Boolean value that specifies whether the access should generate an audit. This member is currently unused by drivers. 


### -field GenerateOnClose

A Boolean value that specifies whether an audit should be generated when the handle being created is closed. This member is currently unused by drivers. 


### -field PrivilegesAllocated

A Boolean value that specifies whether privileges were allocated as part of the access check. This member is currently unused by drivers. 


### -field Flags

A 32-bit value that contains bit-field flags for the access. A driver can check for the traverse access flag (TOKEN_HAS_TRAVERSE_PRIVILEGE). For more information about how to check for traverse access, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/checking-for-traverse-privilege-on-irp-mj-create">Check for Traverse Privilege on IRP_MJ_CREATE</a>. A driver can also check for the TOKEN_IS_RESTRICTED flag. These flags are defined in Ntifs.h. 


### -field RemainingDesiredAccess

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> type that describes the access rights that have not yet been granted to the caller. A driver uses this member to determine if the Windows security system can grant access. If access can be granted, the driver updates the <b>PreviouslyGrantedAccess</b> and <b>RemainingDesiredAccess</b> members accordingly. 


### -field PreviouslyGrantedAccess

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> type that specifies the information about access that has already been granted to the caller of one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563711">Security Reference Monitor Routines</a>. The Windows security system grants certain rights based on the privileges of the caller, such as traverse right (the ability to traverse through a directory as part of opening a subdirectory or file). 


### -field OriginalDesiredAccess

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> type that contains the original access rights that were requested by the caller. 


### -field SubjectSecurityContext

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a> structure that contains information about the subject security context that is used to validate and audit access. 


### -field SecurityDescriptor

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> structure that contains security information for the object that this access relates to. 


### -field AuxData

A pointer to a memory block that contains auxiliary data for the access. 


### -field Privileges

A union that can contain one of the following structures. This union allows three privileges to be embedded in the access state structure. If any more privileges are required during the operation, they will be allocated in the <b>AuxData</b> member extension. This member is currently unused by drivers. 


### -field Privileges.InitialPrivilegeSet

An <a href="https://msdn.microsoft.com/5775c9e9-e647-4544-97e5-45501052b9a9">INITIAL_PRIVILEGE_SET</a> structure that specifies a set of initial privileges for the access. 


### -field Privileges.PrivilegeSet

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551860">PRIVILEGE_SET</a> structure that specifies a set of privileges for the access. 


### -field AuditPrivileges

A Boolean value that specifies whether a privilege usage should be audited. This member is currently unused by drivers. 


### -field ObjectName

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the object name string for the access. This member is used for auditing. 


### -field ObjectTypeName

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the object type name string for the access. This member is used for auditing. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550985">ObOpenObjectByPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551860">PRIVILEGE_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554762">SeAppendPrivileges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554792">SeCaptureSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556682">SeOpenObjectAuditAlarm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556685">SeOpenObjectForDeleteAuditAlarm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556707">SeSetAccessStateGenericMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

