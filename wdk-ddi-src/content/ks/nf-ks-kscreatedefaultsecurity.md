---
UID: NF:ks.KsCreateDefaultSecurity
title: KsCreateDefaultSecurity function (ks.h)
description: The KsCreateDefaultSecurity function creates a security descriptor with default security, optionally inheriting parameters from a parent security descriptor.
old-location: stream\kscreatedefaultsecurity.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsCreateDefaultSecurity function"]
ms.keywords: KsCreateDefaultSecurity, KsCreateDefaultSecurity function [Streaming Media Devices], ks/KsCreateDefaultSecurity, ksfunc_ab036f47-0a15-4983-98b0-7277782f29e6.xml, stream.kscreatedefaultsecurity
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsCreateDefaultSecurity
 - ks/KsCreateDefaultSecurity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsCreateDefaultSecurity
---

# KsCreateDefaultSecurity function


## -description

The <b>KsCreateDefaultSecurity </b>function creates a security descriptor with default security, optionally inheriting parameters from a parent security descriptor.

## -parameters

### -param ParentSecurity 

[in, optional]
Points to the parent object's security descriptor, describing inherited security parameters. This argument is optional.

### -param DefaultSecurity 

[out]
Points to the place in which to put the returned default security descriptor.

## -returns

<b>KsCreateDefaultSecurity</b> returns STATUS_SUCCESS if the operation is successful, else a resource or assignment error.

## -remarks

<b>KsCreateDefaultSecurity</b> is used to initialize subobjects that do not have any stored security.

