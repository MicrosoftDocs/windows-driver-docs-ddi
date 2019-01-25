---
UID: NS:wdm._ACL
title: "_ACL" (wdm.h)
description: The ACL structure is the header of an access-control list (ACL). A complete ACL consists of an ACL structure followed by an ordered list of zero or more access-control entries (ACE).
old-location: ifsk\acl.htm
tech.root: ifsk
ms.assetid: dac27df2-fabd-4402-8daf-9317888dd30b
ms.date: 04/16/2018
ms.keywords: "*PACL, ACL, ACL structure [Installable File System Drivers], PACL, PACL structure pointer [Installable File System Drivers], _ACL, ifsk.acl, securitystructures_a41770ca-4016-400f-8626-e6c8dc92642e.xml, wdm/ACL, wdm/PACL"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
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
-	wdm.h
api_name:
-	ACL
product:
- Windows
targetos: Windows
req.typenames: ACL
---

# _ACL structure


## -description


The ACL structure is the header of an access-control list (ACL). A complete ACL consists of an ACL structure followed by an ordered list of zero or more access-control entries (ACE). 


## -struct-fields




### -field AclRevision

Revision level of the ACL. 

<b>Microsoft Windows NT 4.0 and earlier:</b> This value must be ACL_REVISION. 

<b>Microsoft Windows 2000 and later:</b> This value can be ACL_REVISION or ACL_REVISION_DS. It must be ACL_REVISION_DS if the ACL contains an object-specific ACE. 


### -field Sbz1

A zero byte of padding that aligns the <b>AclRevision</b> member on a 16-bit boundary. 


### -field AclSize

Size, in bytes, of the ACL. This value includes both the ACL structure and all the ACEs. 


### -field AceCount

Number of ACEs stored in the ACL. 


### -field Sbz2

Two zero bytes of padding that align the ACL structure on a 32-bit boundary. 


## -remarks



An ACL includes a sequential list of zero or more ACEs. The individual ACEs in an ACL are numbered from 0 to <i>n</i>, where <i>n</i>+1 is the number of ACEs in the ACL. When editing an ACL, a driver refers to an ACE within the ACL by its index. 

There are two types of ACL: discretionary and system. 

A discretionary ACL (DACL) is controlled by the owner of an object or anyone granted WRITE_DAC access to the object. It specifies the access particular users and groups can have to an object. For example, the owner of a file can use a DACL to control which users and groups can and cannot have access to the file. 

An object may also have system-level security information associated with it, in the form of a system ACL (SACL) controlled by a system administrator. A SACL can allow the system administrator to audit any attempts to gain access to an object. 

Three ACE structures are currently defined: 

<table>
<tr>
<th>Attribute</th>
<th>Description</th>
</tr>
<tr>
<td>
ACCESS_ALLOWED_ACE

</td>
<td>
Grants specified rights to a user or group. This ACE is stored in a DACL.

</td>
</tr>
<tr>
<td>
ACCESS_DENIED_ACE

</td>
<td>
Denies specified rights to a user or group. This ACE is stored in a DACL.

</td>
</tr>
<tr>
<td>
SYSTEM_AUDIT_ACE

</td>
<td>
Specifies what types of access will cause system-level audits. This ACE is stored in a SACL.

</td>
</tr>
</table>
 

A fourth ACE structure, SYSTEM_ALARM_ACE, is not currently supported. 

The ACL structure is to be treated as though it were opaque, and drivers should not attempt to work with its members directly. To ensure that ACLs are semantically correct, drivers can use the functions listed in the See Also section to create and manipulate ACLs. 

ACL and ACE structures must be aligned on 32-bit boundaries. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538796">ACCESS_ALLOWED_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538831">ACCESS_DENIED_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552092">RtlAddAccessAllowedAce</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552151">RtlCreateAcl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552288">RtlGetAce</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562781">RtlSetDaclSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556769">SYSTEM_ALARM_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556771">SYSTEM_AUDIT_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556831">TOKEN_DEFAULT_DACL</a>
 

 

