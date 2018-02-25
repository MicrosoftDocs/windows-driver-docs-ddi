---
UID: NS:ntifs._ACE_HEADER
title: "_ACE_HEADER"
author: windows-driver-content
description: The ACE_HEADER structure describes the type and size of an access-control entry (ACE).
old-location: ifsk\ace_header.htm
old-project: ifsk
ms.assetid: f5f39310-8b15-4d6b-a985-3f25522a16b1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PACE_HEADER, ,, A, ACE_HEADER, ACE_HEADER structure [Installable File System Drivers], C, D, E, H, P, PACE_HEADER, PACE_HEADER structure pointer [Installable File System Drivers], R, _, _ACE_HEADER, ifsk.ace_header, ntifs/ACE_HEADER, ntifs/PACE_HEADER, securitystructures_a5aba00b-54fc-4356-9dc8-bf3d5dbe7f78.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	ACE_HEADER
product: Windows
targetos: Windows
req.typenames: ACE_HEADER
---

# _ACE_HEADER structure


## -description


The ACE_HEADER structure describes the type and size of an access-control entry (ACE). 


## -syntax


````
typedef struct _ACE_HEADER {
  UCHAR  AceType;
  UCHAR  AceFlags;
  USHORT AceSize;
} ACE_HEADER, *PACE_HEADER;
````


## -struct-fields




### -field AceType

ACE type. This member can be one of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ACCESS_ALLOWED_ACE_TYPE

</td>
<td>
Access-allowed ACE that uses the ACCESS_ALLOWED_ACE structure.

</td>
</tr>
<tr>
<td>
ACCESS_DENIED_ACE_TYPE

</td>
<td>
Access-denied ACE that uses the ACCESS_DENIED_ACE structure.

</td>
</tr>
<tr>
<td>
SYSTEM_AUDIT_ACE_TYPE

</td>
<td>
System-audit ACE that uses the SYSTEM_AUDIT_ACE structure.

</td>
</tr>
</table>
 


### -field AceFlags

Set of ACE type-specific control flags. This member can be a combination of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CONTAINER_INHERIT_ACE

</td>
<td>
Child objects that are containers, such as directories, inherit the ACE as an effective ACE. The inherited ACE is inheritable unless the NO_PROPAGATE_INHERIT_ACE bit flag is also set. 

</td>
</tr>
<tr>
<td>
FAILED_ACCESS_ACE_FLAG

</td>
<td>
Used with system-audit ACEs in a SACL to generate audit messages for failed access attempts.

</td>
</tr>
<tr>
<td>
INHERIT_ONLY_ACE

</td>
<td>
Indicates an inherit-only ACE which does not control access to the object to which it is attached. If this flag is not set, the ACE is an effective ACE which controls access to the object to which it is attached. 

Both effective and inherit-only ACEs can be inherited depending on the state of the other inheritance flags. 

</td>
</tr>
<tr>
<td>
INHERITED_ACE

</td>
<td>
<b>Microsoft Windows 2000 or later: </b>Indicates that the ACE was inherited. The system sets this bit when it propagates an inherited ACE to a child object. 

</td>
</tr>
<tr>
<td>
NO_PROPAGATE_INHERIT_ACE

</td>
<td>
If the ACE is inherited by a child object, the system clears the OBJECT_INHERIT_ACE and CONTAINER_INHERIT_ACE flags in the inherited ACE. This prevents the ACE from being inherited by subsequent generations of objects. 

</td>
</tr>
<tr>
<td>
OBJECT_INHERIT_ACE

</td>
<td>
Noncontainer child objects inherit the ACE as an effective ACE. 

For child objects that are containers, the ACE is inherited as an inherit-only ACE unless the NO_PROPAGATE_INHERIT_ACE bit flag is also set.

</td>
</tr>
<tr>
<td>
SUCCESSFUL_ACCESS_ACE_FLAG

</td>
<td>
Used with system-audit ACEs in a SACL to generate audit messages for successful access attempts. 

</td>
</tr>
</table>
 


### -field AceSize

Size, in bytes, of the ACE. 


## -remarks



The ACE_HEADER structure is the first member of the various types of ACE structures, such as ACCESS_ALLOWED_ACE. 

System-alarm ACEs are not currently supported. The <b>AceType</b> member cannot specify the SYSTEM_ALARM_ACE_TYPE. Do not use the SYSTEM_ALARM_ACE structure. 




## -see-also

<a href="..\ntifs\ns-ntifs-_access_allowed_ace.md">ACCESS_ALLOWED_ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="..\ntifs\ns-ntifs-_access_denied_ace.md">ACCESS_DENIED_ACE</a>



<a href="..\ntifs\ns-ntifs-_system_alarm_ace.md">SYSTEM_ALARM_ACE</a>



<a href="..\ntifs\ns-ntifs-_system_audit_ace.md">SYSTEM_AUDIT_ACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20ACE_HEADER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

