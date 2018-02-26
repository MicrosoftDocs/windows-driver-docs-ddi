---
UID: NS:ntifs._TOKEN_SOURCE
title: "_TOKEN_SOURCE"
author: windows-driver-content
description: TOKEN_SOURCE identifies the source of an access token.
old-location: ifsk\token_source.htm
old-project: ifsk
ms.assetid: 0820f6f2-bec2-4d38-9a95-cfff6151ef02
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PTOKEN_SOURCE, ,, C, E, K, N, O, P, PTOKEN_SOURCE, PTOKEN_SOURCE structure pointer [Installable File System Drivers], R, S, T, TOKEN_SOURCE, TOKEN_SOURCE structure [Installable File System Drivers], U, _, _TOKEN_SOURCE, ifsk.token_source, ntifs/PTOKEN_SOURCE, ntifs/TOKEN_SOURCE, securitystructures_caf23dc4-0bfe-40e1-9b94-b58bb0eb893e.xml"
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
-	TOKEN_SOURCE
product: Windows
targetos: Windows
req.typenames: TOKEN_SOURCE, *PTOKEN_SOURCE
---

# _TOKEN_SOURCE structure


## -description


TOKEN_SOURCE identifies the source of an access token. 


## -syntax


````
typedef struct _TOKEN_SOURCE {
  CHAR SourceName[TOKEN_SOURCE_LENGTH];
  LUID SourceIdentifier;
} TOKEN_SOURCE, *PTOKEN_SOURCE;
````


## -struct-fields




### -field SourceName

Specifies an 8-byte character string used to identify the source of an access token. This is used to distinguish between such sources as Session Manager, LAN Manager, and RPC Server. A string, rather than a constant, is used to identify the source so users and developers can make extensions to the system, such as by adding other networks, that act as the source of access tokens. Note that TOKEN_SOURCE_LENGTH currently equals 8.


### -field SourceIdentifier

Specifies a locally unique identifier (LUID) provided by the source component named by the <b>SourceName</b> member. This value aids the source component in relating context blocks, such as session-control structures, to the token. This value is typically, but not necessarily, an LUID. 


## -see-also

<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_SOURCE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

