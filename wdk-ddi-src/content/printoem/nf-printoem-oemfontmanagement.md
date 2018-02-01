---
UID: NF:printoem.OEMFontManagement
title: OEMFontManagement function
author: windows-driver-content
description: The OEMFontManagement function is an optional entry point provided for PostScript devices.
old-location: print\oemfontmanagement.htm
old-project: print
ms.assetid: fd4e712a-8bde-4c80-b288-3fa7b69a2681
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: OEMFontManagement, print_unidrv-pscript_rendering_41e19fb2-9946-4911-beb2-3681bd08c08b.xml, OEMFontManagement function [Print Devices], printoem/OEMFontManagement, print.oemfontmanagement
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
-	OEMFontManagement
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMFontManagement function


## -description


The <code>OEMFontManagement</code> function is an optional entry point provided for PostScript devices. 


## -syntax


````
ULONG APIENTRY OEMFontManagement(
        SURFOBJ                     *pso,
        FONTOBJ                     *pfo,
        ULONG                       iMode,
        ULONG                       cjIn,
  _In_  _reads_bytes_(cjIn) PVOID   pvIn,
        ULONG                       cjOut,
  _Out_ _writes_bytes_(cjOut) PVOID pvOut
);
````


## -parameters




### -param pso



### -param pfo



### -param iMode



### -param cjIn



### -param pvIn [in]



### -param cjOut



### -param pvOut [out]


