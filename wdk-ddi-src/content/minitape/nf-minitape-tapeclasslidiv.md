---
UID: NF:minitape.TapeClassLiDiv
title: TapeClassLiDiv function
author: windows-driver-content
description: The TapeClassLiDiv routine performs a division of the two indicated integers.
old-location: storage\tapeclasslidiv.htm
old-project: storage
ms.assetid: 13c449c6-6e2b-434e-8948-62c8af237173
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: tapeclas_8c5ecef8-fdd0-4889-8e3f-1bd80fe5b5c6.xml, storage.tapeclasslidiv, TapeClassLiDiv, minitape/TapeClassLiDiv, TapeClassLiDiv routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: minitape.h
req.include-header: Minitape.h
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
req.lib: Tape.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Tape.lib
-	Tape.dll
apiname:
-	TapeClassLiDiv
product: Windows
targetos: Windows
req.typenames: "*PTAPE_STATUS, TAPE_STATUS"
---

# TapeClassLiDiv function


## -description


The <b>TapeClassLiDiv</b> routine performs a division of the two indicated integers. 


## -syntax


````
LARGE_INTEGER TapeClassLiDiv(
  _In_ LARGE_INTEGER Dividend,
  _In_ LARGE_INTEGER Divisor
);
````


## -parameters




### -param Dividend [in]

Contains the dividend.


### -param Divisor [in]

Contains the divisor.


## -returns


<b>TapeClassLiDiv</b> returns the result of the division. 


