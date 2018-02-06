---
UID: NF:printoem.OEMEnablePDEV
title: OEMEnablePDEV function
author: windows-driver-content
description: OEMEnablePDEV function
old-location: print\oemenablepdev.htm
old-project: print
ms.assetid: 0088f5f6-eb68-4081-8cca-3d34fd10593a
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMEnablePDEV function [Print Devices], print_obsoletefunctions_f6d0b164-0458-442f-ac6a-791592883196.xml, print.oemenablepdev, printoem/OEMEnablePDEV, OEMEnablePDEV
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
-	OEMEnablePDEV
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMEnablePDEV function


## -description




## -syntax


````
PDEVOEM APIENTRY OEMEnablePDEV(
          PDEVOBJ                            pdevobj,
  _In_    PWSTR                              pPrinterName,
          ULONG                              cPatterns,
  _In_    _updates_(cPatterns) HSURF         *phsurfPatterns,
          ULONG                              cjGdiInfo,
  _Inout_ _updates_bytes_(cjGdiInfo) GDIINFO *pGdiInfo,
          ULONG                              cjDevInfo,
  _Inout_ _updates_bytes_(cjDevInfo) DEVINFO *pDevInfo,
  _In_    DRVENABLEDATA                      *pded
);
````


## -parameters




### -param pdevobj



### -param pPrinterName [in]



### -param cPatterns



### -param phsurfPatterns [in]



### -param cjGdiInfo



### -param pGdiInfo [in, out]



### -param cjDevInfo



### -param pDevInfo [in, out]



### -param pded [in]


