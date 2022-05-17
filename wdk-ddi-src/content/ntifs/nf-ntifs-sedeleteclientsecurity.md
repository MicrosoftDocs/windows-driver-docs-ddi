---
UID: NF:ntifs.SeDeleteClientSecurity
title: SeDeleteClientSecurity macro (ntifs.h)
description: The SeDeleteClientSecurity routine deletes a client security context.
old-location: ifsk\sedeleteclientsecurity.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["SeDeleteClientSecurity macro"]
ms.keywords: SeDeleteClientSecurity, SeDeleteClientSecurity routine [Installable File System Drivers], ifsk.sedeleteclientsecurity, ntifs/SeDeleteClientSecurity, seref_bab4478e-d302-478b-8819-79c9b2f79aa7.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SeDeleteClientSecurity
 - ntifs/SeDeleteClientSecurity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SeDeleteClientSecurity
---

# SeDeleteClientSecurity macro

## -description

The **SeDeleteClientSecurity** routine deletes a client security context.

## -parameters

### -param ClientContext

Pointer to the client security context structure to be deleted.

## -remarks

**SeDeleteClientSecurity** deletes a client security context structure and performs any necessary cleanup, such as removing any client token references.

Each call to **SeCreateClientSecurity** or **SeCreateClientSecurityFromSubjectContext** must be matched by a subsequent call to **SeDeleteClientSecurity**.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[**SeCreateClientSecurity**](nf-ntifs-secreateclientsecurity.md)

[**SeCreateClientSecurityFromSubjectContext**](nf-ntifs-secreateclientsecurityfromsubjectcontext.md)
