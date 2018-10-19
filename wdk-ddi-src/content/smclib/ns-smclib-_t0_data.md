---
UID: NS:smclib._T0_DATA
title: "_T0_DATA"
author: windows-driver-content
description: The T0_DATA structure is used by the smart card driver library to process T0 I/O.
old-location: smartcrd\t0_data.htm
tech.root: smartcrd
ms.assetid: CC827018-F6B2-48DF-BF0A-36654F866BD9
ms.date: 02/22/2018
ms.keywords: "*PT0_DATA, PT0_DATA, PT0_DATA structure pointer [Smart Card Reader Devices], T0_DATA, T0_DATA structure [Smart Card Reader Devices], _T0_DATA, smartcrd.t0_data, smclib/PT0_DATA, smclib/T0_DATA"
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
-	Smclib.h
api_name:
-	T0_DATA
product:
- Windows
targetos: Windows
req.typenames: T0_DATA, *PT0_DATA
---

# _T0_DATA structure


## -description


The T0_DATA structure is used by the smart card driver library to process T0 I/O. 


## -struct-fields




### -field Lc

Number of data bytes in the request.


### -field Le

Number of expected bytes from the card.

