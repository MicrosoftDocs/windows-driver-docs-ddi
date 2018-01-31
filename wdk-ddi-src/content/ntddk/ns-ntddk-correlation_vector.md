---
UID: NS:ntddk.CORRELATION_VECTOR
title: CORRELATION_VECTOR
author: windows-driver-content
description: Store the correlation vector that is used to reference events and the generated logs for diagnostic purposes.
old-location: kernel\correlation_vector.htm
old-project: kernel
ms.assetid: 35c1799f-2012-42b0-95e6-6902c818a094
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: CORRELATION_VECTOR, *PCORRELATION_VECTOR, ntddk/CORRELATION_VECTOR, CORRELATION_VECTOR structure [Kernel-Mode Driver Architecture], kernel.correlation_vector
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	CORRELATION_VECTOR
product: Windows
targetos: Windows
req.typenames: CORRELATION_VECTOR
---

# CORRELATION_VECTOR structure


## -description


Store the correlation vector that is used to reference events and the generated logs
    for diagnostic purposes.


## -syntax


````
typedef struct _CORRELATION_VECTOR {
  CHAR  Version;
  CHAR  Vector[RTL_CORRELATION_VECTOR_STRING_LENGTH];
} CORRELATION_VECTOR;
````


## -struct-fields




#### - Version

The version of the correlation vector. Possible values are: 
<ul>
<li>RTL_CORRELATION_VECTOR_VERSION_1</li>
<li>RTL_CORRELATION_VECTOR_VERSION_2</li>
<li>RTL_CORRELATION_VECTOR_VERSION_CURRENT</li>
</ul>

#### - Vector

An array CHARs that represents the correlation vector.

