---
UID: NS:ntifs._SID
title: "_SID" (ntifs.h)
description: The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups.
old-location: ifsk\sid.htm
tech.root: ifsk
ms.assetid: 3b0d68f9-e871-42fe-97b0-f70f1fa72bf0
ms.date: 04/16/2018
ms.keywords: "*PISID, PSID, PSID structure pointer [Installable File System Drivers], SID, SID structure [Installable File System Drivers], _SID, ifsk.sid, ntifs/PSID, ntifs/SID, securitystructures_748be9da-f428-42cd-a1f8-eca090e2b3aa.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	SID
product:
- Windows
targetos: Windows
req.typenames: SID, *PISID
---

# _SID structure


## -description


The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups.

Drivers are not to modify the SID structure directly. To create and manipulate a security identifier, use the support routines listed in the See Also section. 


## -struct-fields




### -field Revision


### -field SubAuthorityCount


### -field IdentifierAuthority


### -field SubAuthority.size_is

 


### -field SubAuthority.size_is.SubAuthorityCount

 


### -field SubAuthority


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552146">RtlCopySid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552256">RtlEqualPrefixSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552260">RtlEqualSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552976">RtlGetOwnerSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552998">RtlInitializeSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553085">RtlLengthSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553220">RtlSetOwnerSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553236">RtlSubAuthoritySid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553314">RtlValidSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556743">SID_IDENTIFIER_AUTHORITY</a>
 

 

