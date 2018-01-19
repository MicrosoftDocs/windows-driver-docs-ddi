---
UID: NS:ntifs._ACCESS_ALLOWED_ACE
title: _ACCESS_ALLOWED_ACE
author: windows-driver-content
description: The ACCESS_ALLOWED_ACE structure defines an access-control entry (ACE) for the discretionary access-control list (DACL) that controls access to an object.
old-location: ifsk\access_allowed_ace.htm
old-project: ifsk
ms.assetid: 20373863-0850-4ccf-b94a-7d252ad15d20
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _ACCESS_ALLOWED_ACE, ACCESS_ALLOWED_ACE, *PACCESS_ALLOWED_ACE
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
req.alt-api: ACCESS_ALLOWED_ACE
req.alt-loc: ntifs.h
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
req.typenames: ACCESS_ALLOWED_ACE
---

# _ACCESS_ALLOWED_ACE structure



## -description
The ACCESS_ALLOWED_ACE structure defines an access-control entry (ACE) for the discretionary access-control list (DACL) that controls access to an object. An access-allowed ACE allows access to an object for a specific subject identified by a security identifier (SID). 



## -syntax

````
typedef struct _ACCESS_ALLOWED_ACE {
  ACE_HEADER  Header;
  ACCESS_MASK Mask;
  ULONG       SidStart;
} ACCESS_ALLOWED_ACE, *PACCESS_ALLOWED_ACE;
````


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
<dl>
<dt>
<a href="..\ntifs\ns-ntifs-_access_denied_ace.md">ACCESS_DENIED_ACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_ace_header.md">ACE_HEADER</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_acl.md">ACL</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_system_alarm_ace.md">SYSTEM_ALARM_ACE</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_system_audit_ace.md">SYSTEM_AUDIT_ACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20ACCESS_ALLOWED_ACE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

