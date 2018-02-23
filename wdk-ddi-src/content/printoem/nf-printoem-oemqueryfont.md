---
UID: NF:printoem.OEMQueryFont
title: OEMQueryFont function
author: windows-driver-content
description: The OEMQueryFont function is used by GDI to get the IFIMETRICS structure for a given font.
old-location: print\oemqueryfont.htm
old-project: print
ms.assetid: cee6b2dd-e79b-4372-8371-c57fe950de88
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: OEMQueryFont, printoem/OEMQueryFont, OEMQueryFont function [Print Devices], print.oemqueryfont, print_unidrv-pscript_rendering_52b50b2d-ab61-420f-be04-7285a5504be6.xml
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
-	OEMQueryFont
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMQueryFont function


## -description


The <code>OEMQueryFont</code> function is used by GDI to get the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567418">IFIMETRICS</a> structure for a given font. 


## -syntax


````
PIFIMETRICS APIENTRY OEMQueryFont(
   DHPDEV    dhpdev,
   ULONG_PTR iFile,
   ULONG     iFace,
   ULONG_PTR *pid
);
````


## -parameters




### -param dhpdev


### -param iFile


### -param iFace


### -param pid

