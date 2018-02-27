---
UID: NC:printoem.PFN_DrvUpdateUISetting
title: PFN_DrvUpdateUISetting
author: windows-driver-content
description: The DrvUpdateUISetting function is obsolete.
old-location: print\drvupdateuisetting.htm
old-project: print
ms.assetid: 37f8ab73-ff81-4150-b1f6-faec5ca76908
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DrvUpdateUISetting, DrvUpdateUISetting callback function [Print Devices], PFN_DrvUpdateUISetting, print.drvupdateuisetting, print_obsoletefunctions_8982b302-4efb-4a54-a3ae-a27c2dd0baa9.xml, printoem/DrvUpdateUISetting
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: printoem.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	printoem.h
apiname:
-	DrvUpdateUISetting
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# PFN_DrvUpdateUISetting callback


## -description


The <b>DrvUpdateUISetting</b> function is obsolete.

 Windows 2000 and later UI plug-ins should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553115">IPrintOemDriverUI::DrvUpdateUISetting</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553039">IPrintCoreUI2::DrvUpdateUISetting</a>. 

This function pointer prototype defines the type of the <b>DrvUpdateUISetting</b> member of the <a href="..\printoem\ns-printoem-_oemuiprocs.md">OEMUIPROCS</a> structure.


## -prototype


````
PFN_DrvUpdateUISetting DrvUpdateUISetting;

 BOOL APIENTRY* DrvUpdateUISetting(
   PVOID pdriverobj,
   PVOID pOptItem,
   DWORD dwPreviousSelection,
   DWORD dwMode
)
{ ... }
````


## -parameters




### -param pdriverobj


### -param pOptItem


### -param dwPreviousSelection


### -param dwMode

