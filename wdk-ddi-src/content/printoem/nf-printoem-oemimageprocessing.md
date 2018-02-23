---
UID: NF:printoem.OEMImageProcessing
title: OEMImageProcessing function
author: windows-driver-content
description: OEMImageProcessing function
old-location: print\oemimageprocessing.htm
old-project: print
ms.assetid: 965e17bc-2a38-4caa-a0dd-41ee1e1198f0
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: OEMImageProcessing, OEMImageProcessing function [Print Devices], printoem/OEMImageProcessing, print.oemimageprocessing, print_obsoletefunctions_c65011ae-a69c-4cbe-88a8-13847401c7df.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMImageProcessing
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMImageProcessing function


## -description




## -syntax


````
PBYTE APIENTRY OEMImageProcessing(
   PDEVOBJ           pdevobj,
   PBYTE             pSrcBitmap,
   PBITMAPINFOHEADER pBitmapInfoHeader,
   PBYTE             pColorTable,
   DWORD             dwCallbackID,
   PIPPARAMS         pIPParams
);
````


## -parameters




### -param pdevobj


### -param pSrcBitmap


### -param pBitmapInfoHeader


### -param pColorTable


### -param dwCallbackID


### -param pIPParams

