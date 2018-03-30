---
UID: NS:ntifs._TOKEN_PRIMARY_GROUP
title: "_TOKEN_PRIMARY_GROUP"
author: windows-driver-content
description: TOKEN_PRIMARY_GROUP specifies a group security identifier (SID) for an access token.
old-location: ifsk\token_primary_group.htm
old-project: ifsk
ms.assetid: 9c9a7f63-7fe8-48a9-b4d0-10586e6b86bc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_PRIMARY_GROUP, PTOKEN_PRIMARY_GROUP, PTOKEN_PRIMARY_GROUP structure pointer [Installable File System Drivers], TOKEN_PRIMARY_GROUP, TOKEN_PRIMARY_GROUP structure [Installable File System Drivers], _TOKEN_PRIMARY_GROUP, ifsk.token_primary_group, ntifs/PTOKEN_PRIMARY_GROUP, ntifs/TOKEN_PRIMARY_GROUP, securitystructures_8d3bc1f9-abc5-4ac3-8351-cf2c56db6a20.xml"
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
-	TOKEN_PRIMARY_GROUP
product: Windows
targetos: Windows
req.typenames: TOKEN_PRIMARY_GROUP, *PTOKEN_PRIMARY_GROUP
---

# _TOKEN_PRIMARY_GROUP structure


## -description


TOKEN_PRIMARY_GROUP specifies a group security identifier (SID) for an access token. 


## -struct-fields




### -field PrimaryGroup

Pointer to a SID structure representing a group that will become the primary group of any objects created by a process using this access token. The SID must be one of the group SIDs already in the token. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556838">TOKEN_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

