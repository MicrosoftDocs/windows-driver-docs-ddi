---
UID: NF:ks.KsCreateDefaultSecurity
title: KsCreateDefaultSecurity function
author: windows-driver-content
description: The KsCreateDefaultSecurity function creates a security descriptor with default security, optionally inheriting parameters from a parent security descriptor.
old-location: stream\kscreatedefaultsecurity.htm
old-project: stream
ms.assetid: 2992a62b-7c3c-4bf5-ba3a-26c26c419f98
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsCreateDefaultSecurity, KsCreateDefaultSecurity function [Streaming Media Devices], ksfunc_ab036f47-0a15-4983-98b0-7277782f29e6.xml, stream.kscreatedefaultsecurity, KsCreateDefaultSecurity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsCreateDefaultSecurity
product: Windows
targetos: Windows
req.typenames: 
---

# KsCreateDefaultSecurity function


## -description


The <b>KsCreateDefaultSecurity </b>function creates a security descriptor with default security, optionally inheriting parameters from a parent security descriptor.


## -syntax


````
NTSTATUS KsCreateDefaultSecurity(
  _In_opt_ PSECURITY_DESCRIPTOR ParentSecurity,
  _Out_    PSECURITY_DESCRIPTOR *DefaultSecurity
);
````


## -parameters




### -param ParentSecurity [in, optional]

Points to the parent object's security descriptor, describing inherited security parameters. This argument is optional.


### -param DefaultSecurity [out]

Points to the place in which to put the returned default security descriptor.


## -returns



<b>KsCreateDefaultSecurity</b> returns STATUS_SUCCESS if the operation is successful, else a resource or assignment error.




## -remarks



<b>KsCreateDefaultSecurity</b> is used to initialize subobjects that do not have any stored security. 



