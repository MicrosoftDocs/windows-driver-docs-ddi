---
UID: NS:ntifs._TOKEN_DEFAULT_DACL
title: "_TOKEN_DEFAULT_DACL"
author: windows-driver-content
description: The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL).
old-location: ifsk\token_default_dacl.htm
old-project: ifsk
ms.assetid: db4c23e1-4a49-4864-9eab-36abb2581e58
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "_TOKEN_DEFAULT_DACL, PTOKEN_DEFAULT_DACL structure pointer [Installable File System Drivers], ntifs/PTOKEN_DEFAULT_DACL, *PTOKEN_DEFAULT_DACL, TOKEN_DEFAULT_DACL structure [Installable File System Drivers], TOKEN_DEFAULT_DACL, ifsk.token_default_dacl, ntifs/TOKEN_DEFAULT_DACL, securitystructures_a79d9155-eff5-457f-8036-c3d718b36c4e.xml, PTOKEN_DEFAULT_DACL"
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
-	TOKEN_DEFAULT_DACL
product: Windows
targetos: Windows
req.typenames: "*PTOKEN_DEFAULT_DACL, TOKEN_DEFAULT_DACL"
---

# _TOKEN_DEFAULT_DACL structure


## -description


The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL). 


## -syntax


````
typedef struct _TOKEN_DEFAULT_DACL {
  PACL DefaultDacl;
} TOKEN_DEFAULT_DACL, *PTOKEN_DEFAULT_DACL;
````


## -struct-fields




#### - DefaultDacl

Pointer to an access control list (ACL) structure assigned by default to any objects created by the user represented by the access token. 


## -remarks


The <b>SeQueryInformationToken</b> support routine retrieves the default DACL for an access token, in the form of a TOKEN_DEFAULT_DACL structure. 



## -see-also

<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>

<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_DEFAULT_DACL structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

