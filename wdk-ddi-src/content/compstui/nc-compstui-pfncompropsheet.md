---
UID: NC:compstui.PFNCOMPROPSHEET
title: PFNCOMPROPSHEET
author: windows-driver-content
description: Pointer to the common UI callback function to add, delete, or set user data.
old-location: print\pfncomppropsheet.htm
old-project: print
ms.assetid: EFA26AD2-39F6-44B9-9D40-732D22858339
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.pfncomppropsheet, PFNCOMPPROPSHEET, pfnComPropSheet callback function [Print Devices], pfnComPropSheet, PFNCOMPROPSHEET, PFNCOMPROPSHEET, compstui/pfnComPropSheet
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: compstui.h
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
-	Compstui.h
apiname:
-	pfnComPropSheet
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFNCOMPROPSHEET callback


## -description


Pointer to the common UI callback function to add, delete, or set user data. For each function index, it passes a handle, a Function, and two long parameters.


## -prototype


````
PFNCOMPROPSHEET pfnComPropSheet;

LONG_PTR pfnComPropSheet(
   HANDLE hComPropSheet,
   UINT   Function,
   LPARAM lParam1,
   LPARAM lParam2
)
{ ... }
````


## -parameters




### -param hComPropSheet


### -param Function


### -param lParam1


### -param lParam2

