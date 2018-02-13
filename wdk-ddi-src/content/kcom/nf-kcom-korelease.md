---
UID: NF:kcom.KoRelease
title: KoRelease function
author: windows-driver-content
description: The KoRelease function decrements the reference count for the calling interface on an object.
old-location: stream\korelease.htm
old-project: stream
ms.assetid: 59be582c-0f56-45d8-b407-e588ee0f7f8b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KoRelease function [Streaming Media Devices], ksfunc_5a688121-dc73-48fe-8b85-1f6c14fb3a22.xml, kcom/KoRelease, stream.korelease, KoRelease
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: kcom.h
req.include-header: Kcom.h
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
-	KoRelease
product: Windows
targetos: Windows
req.typenames: CONNECT_DATA, *PCONNECT_DATA
---

# KoRelease function


## -description


<i>This function is intended for internal use only.</i>

The <b>KoRelease</b> function decrements the reference count for the calling interface on an object. 


## -syntax


````
void KoRelease(
  _In_ REFCLSID ClassId
);
````


## -parameters




### -param ClassId [in]

The CLSID of the object whose reference count will be decremented.


## -returns



None



