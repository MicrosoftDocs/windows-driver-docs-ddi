---
UID: NS:ntifs._TOKEN_DEFAULT_DACL
title: "_TOKEN_DEFAULT_DACL"
author: windows-driver-content
description: The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL).
old-location: ifsk\token_default_dacl.htm
old-project: ifsk
ms.assetid: db4c23e1-4a49-4864-9eab-36abb2581e58
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_DEFAULT_DACL, PTOKEN_DEFAULT_DACL, PTOKEN_DEFAULT_DACL structure pointer [Installable File System Drivers], TOKEN_DEFAULT_DACL, TOKEN_DEFAULT_DACL structure [Installable File System Drivers], _TOKEN_DEFAULT_DACL, ifsk.token_default_dacl, ntifs/PTOKEN_DEFAULT_DACL, ntifs/TOKEN_DEFAULT_DACL, securitystructures_a79d9155-eff5-457f-8036-c3d718b36c4e.xml"
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
-	TOKEN_DEFAULT_DACL
product: Windows
targetos: Windows
req.typenames: TOKEN_DEFAULT_DACL, *PTOKEN_DEFAULT_DACL
---

# _TOKEN_DEFAULT_DACL structure


## -description


The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL). 


## -struct-fields




### -field DefaultDacl

Pointer to an access control list (ACL) structure assigned by default to any objects created by the user represented by the access token. 


## -remarks



The <b>SeQueryInformationToken</b> support routine retrieves the default DACL for an access token, in the form of a TOKEN_DEFAULT_DACL structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

