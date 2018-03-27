---
UID: NC:ks.PFNQUERYREFERENCESTRING
title: PFNQUERYREFERENCESTRING
author: windows-driver-content
description: This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using ExFreePool.
old-location: stream\kstrqueryreferencestring.htm
old-project: stream
ms.assetid: 08fd750f-19cc-4d78-a26b-9f790c5c3acf
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrQueryReferenceString, KStrQueryReferenceString routine [Streaming Media Devices], PFNQUERYREFERENCESTRING, ks/KStrQueryReferenceString, ksfunc_ce750f42-efeb-4861-b451-ef0f8be40f9a.xml, stream.kstrqueryreferencestring
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h, Swenum.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	KStrQueryReferenceString
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNQUERYREFERENCESTRING callback


## -description


This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>.


## -parameters




### -param Context [in]

Pointer to a device extension of the device's PDO.


### -param *String [in, out]

Pointer to a string containing the reference string associated with the PDO.


## -returns



None.




## -remarks



The driver can access this method through the <b>QueryReferenceString</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557584">BUS_INTERFACE_REFERENCE</a> structure.



