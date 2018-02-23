---
UID: NS:wdm._ACL
title: "_ACL"
author: windows-driver-content
description: The ACL structure is the header of an access-control list (ACL). A complete ACL consists of an ACL structure followed by an ordered list of zero or more access-control entries (ACE).
old-location: ifsk\acl.htm
old-project: ifsk
ms.assetid: dac27df2-fabd-4402-8daf-9317888dd30b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ACL structure [Installable File System Drivers], wdm/ACL, _ACL, wdm/PACL, PACL structure pointer [Installable File System Drivers], ACL, ifsk.acl, *PACL, securitystructures_a41770ca-4016-400f-8626-e6c8dc92642e.xml, PACL
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	ACL
product: Windows
targetos: Windows
req.typenames: ACL
req.product: Windows 10 or later.
---

# _ACL structure


## -description


The ACL structure is the header of an access-control list (ACL). A complete ACL consists of an ACL structure followed by an ordered list of zero or more access-control entries (ACE). 


## -syntax


````
typedef struct _ACL {
  UCHAR  AclRevision;
  UCHAR  Sbz1;
  USHORT AclSize;
  USHORT AceCount;
  USHORT Sbz2;
} ACL, *PACL;
````


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

<a href="..\ntifs\ns-ntifs-_system_audit_ace.md">SYSTEM_AUDIT_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="..\ntifs\ns-ntifs-_token_default_dacl.md">TOKEN_DEFAULT_DACL</a>



<a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>



<a href="..\ntifs\ns-ntifs-_access_denied_ace.md">ACCESS_DENIED_ACE</a>



<a href="..\ntifs\ns-ntifs-_access_allowed_ace.md">ACCESS_ALLOWED_ACE</a>



<a href="..\ntifs\nf-ntifs-rtlcreateacl.md">RtlCreateAcl</a>



<a href="..\ntifs\nf-ntifs-rtlgetace.md">RtlGetAce</a>



<a href="..\ntifs\ns-ntifs-_token_default_dacl.md">TOKEN_DEFAULT_DACL</a>



<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20ACL structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

