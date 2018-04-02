---
UID: NS:ntifs._TOKEN_GROUPS
title: "_TOKEN_GROUPS"
author: windows-driver-content
description: TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token.
old-location: ifsk\token_groups.htm
old-project: ifsk
ms.assetid: 08faebdf-7e6d-4da4-a4c2-a0b57de437ce
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PTOKEN_GROUPS, PTOKEN_GROUPS, PTOKEN_GROUPS structure pointer [Installable File System Drivers], TOKEN_GROUPS, TOKEN_GROUPS structure [Installable File System Drivers], _TOKEN_GROUPS, ifsk.token_groups, ntifs/PTOKEN_GROUPS, ntifs/TOKEN_GROUPS, securitystructures_97d0491f-87b4-4e76-8252-fad37cc94c1c.xml"
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
-	TOKEN_GROUPS
product: Windows
targetos: Windows
req.typenames: TOKEN_GROUPS, *PTOKEN_GROUPS
---

# _TOKEN_GROUPS structure


## -description


TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token. 


## -struct-fields




### -field GroupCount

Specifies the number of groups in the access token. 


### -field Groups

Specifies an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a> structures containing a set of SIDs and corresponding attributes. 


## -remarks



You can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a> to designate one or more group SIDs as deny-only SIDs. Note that it is also possible to designate a user SID as a deny-only SID by specifying the user SID as one of the group SIDs in the <b>TOKEN_GROUPS</b> structure passed to <b>SeFilterToken</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

