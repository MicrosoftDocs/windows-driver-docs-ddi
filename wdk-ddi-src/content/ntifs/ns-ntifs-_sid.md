---
UID: NS:ntifs._SID
title: "_SID"
author: windows-driver-content
description: The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups.
old-location: ifsk\sid.htm
old-project: ifsk
ms.assetid: 3b0d68f9-e871-42fe-97b0-f70f1fa72bf0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PISID, PSID, PSID structure pointer [Installable File System Drivers], SID, SID structure [Installable File System Drivers], _SID, ifsk.sid, ntifs/PSID, ntifs/SID, securitystructures_748be9da-f428-42cd-a1f8-eca090e2b3aa.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	SID
product: Windows
targetos: Windows
req.typenames: SID, *PISID
---

# _SID structure


## -description


The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups.

Drivers are not to modify the SID structure directly. To create and manipulate a security identifier, use the support routines listed in the See Also section. 


## -syntax


````
typedef struct _SID {
  UCHAR                    Revision;
  UCHAR                    SubAuthorityCount;
  SID_IDENTIFIER_AUTHORITY IdentifierAuthority;
  ULONG                    SubAuthority[ANYSIZE_ARRAY];
} SID, *PSID;
````


## -struct-fields




### -field Revision


### -field SubAuthorityCount


### -field IdentifierAuthority


### -field SubAuthority


## -see-also

<a href="..\ntifs\nf-ntifs-rtlvalidsid.md">RtlValidSid</a>



<a href="..\ntifs\ns-ntifs-_sid_identifier_authority.md">SID_IDENTIFIER_AUTHORITY</a>



<a href="..\ntifs\nf-ntifs-rtlequalprefixsid.md">RtlEqualPrefixSid</a>



<a href="..\ntifs\nf-ntifs-rtlequalsid.md">RtlEqualSid</a>



<a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a>



<a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>



<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>



<a href="..\ntifs\ns-ntifs-_sid_and_attributes.md">SID_AND_ATTRIBUTES</a>



<a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a>



<a href="..\ntifs\nf-ntifs-rtlcopysid.md">RtlCopySid</a>



<a href="..\ntifs\nf-ntifs-rtlgetownersecuritydescriptor.md">RtlGetOwnerSecurityDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SID structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

