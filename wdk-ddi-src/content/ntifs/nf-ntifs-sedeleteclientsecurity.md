---
UID: NF:ntifs.SeDeleteClientSecurity
title: SeDeleteClientSecurity macro
author: windows-driver-content
description: The SeDeleteClientSecurity routine deletes a client security context.
old-location: ifsk\sedeleteclientsecurity.htm
old-project: ifsk
ms.assetid: 413469b9-2f6c-4f4d-8723-80645a72744c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeDeleteClientSecurity, SeDeleteClientSecurity routine [Installable File System Drivers], ifsk.sedeleteclientsecurity, ntifs/SeDeleteClientSecurity, seref_bab4478e-d302-478b-8819-79c9b2f79aa7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	SeDeleteClientSecurity
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeDeleteClientSecurity macro


## -description


The <b>SeDeleteClientSecurity</b> routine deletes a client security context.


## -syntax


````
VOID SeDeleteClientSecurity(
  _In_ PSECURITY_CLIENT_CONTEXT ClientContext
);
````


## -parameters




### -param C

TBD






#### - ClientContext [in]

Pointer to the client security context structure to be deleted.


## -remarks



<b>SeDeleteClientSecurity</b> deletes a client security context structure and performs any necessary cleanup, such as removing any client token references.

Each call to <b>SeCreateClientSecurity</b> or <b>SeCreateClientSecurityFromSubjectContext</b> must be matched by a subsequent call to <b>SeDeleteClientSecurity</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\ntifs\nf-ntifs-secreateclientsecurityfromsubjectcontext.md">SeCreateClientSecurityFromSubjectContext</a>



<a href="..\ntifs\nf-ntifs-secreateclientsecurity.md">SeCreateClientSecurity</a>



 

 


