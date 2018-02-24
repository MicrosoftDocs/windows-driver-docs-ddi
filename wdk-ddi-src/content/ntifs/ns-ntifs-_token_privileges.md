---
UID: NS:ntifs._TOKEN_PRIVILEGES
title: "_TOKEN_PRIVILEGES"
author: windows-driver-content
description: TOKEN_PRIVILEGES contains information about a set of privileges for an access token.
old-location: ifsk\token_privileges.htm
old-project: ifsk
ms.assetid: f2f4b2b7-bec0-42c3-904b-cbc74ca76bb3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_PRIVILEGES, PTOKEN_PRIVILEGES structure pointer [Installable File System Drivers], ifsk.token_privileges, _TOKEN_PRIVILEGES, ntifs/PTOKEN_PRIVILEGES, PTOKEN_PRIVILEGES, TOKEN_PRIVILEGES structure [Installable File System Drivers], securitystructures_3da1d9ba-6fa7-4b16-bdd7-416890b57f7e.xml, TOKEN_PRIVILEGES, ntifs/TOKEN_PRIVILEGES"
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
-	TOKEN_PRIVILEGES
product: Windows
targetos: Windows
req.typenames: "*PTOKEN_PRIVILEGES, TOKEN_PRIVILEGES"
---

# _TOKEN_PRIVILEGES structure


## -description


TOKEN_PRIVILEGES contains information about a set of privileges for an access token. 


## -syntax


````
typedef struct _TOKEN_PRIVILEGES {
  ULONG               PrivilegeCount;
  LUID_AND_ATTRIBUTES Privileges[ANYSIZE_ARRAY];
} TOKEN_PRIVILEGES, *PTOKEN_PRIVILEGES;
````


## -struct-fields




### -field PrivilegeCount

Specifies the number of entries in the <b>Privileges</b> array. 


### -field Privileges

Specifies an array of LUID_AND_ATTRIBUTES structures. Each structure contains the LUID and attributes of a privilege. 


## -see-also

<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



<a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>



<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_PRIVILEGES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

