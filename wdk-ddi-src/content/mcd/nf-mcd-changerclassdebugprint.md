---
UID: NF:mcd.ChangerClassDebugPrint
title: ChangerClassDebugPrint function (mcd.h)
description: The ChangerClassDebugPrint function prints debugging information.
old-location: storage\changerclassdebugprint.htm
tech.root: storage
ms.assetid: 452377f1-a926-4f43-8168-bea11622902e
ms.date: 03/29/2018
keywords: ["ChangerClassDebugPrint function"]
ms.keywords: ChangerClassDebugPrint, ChangerClassDebugPrint function [Storage Devices], chgrclas_3372885c-482b-4dab-87ae-e59668e91950.xml, mcd/ChangerClassDebugPrint, storage.changerclassdebugprint
f1_keywords:
 - "mcd/ChangerClassDebugPrint"
 - "ChangerClassDebugPrint"
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Mcd.lib
- Mcd.dll
api_name:
- ChangerClassDebugPrint
targetos: Windows
req.typenames: 
---

# ChangerClassDebugPrint function


## -description


The <b>ChangerClassDebugPrint</b> function prints debugging information. 


## -parameters




### -param DebugPrintLevel

Indicates how verbose debug information should be. Caller must assign this parameter an integer value between zero and three, where three specifies the highest level of verbosity and zero the lowest. 


### -param DebugMessage

Caller can specify a message to be included with the debugging information that is printed by assigning a printable ASCII character string to this parameter.


### -param param

TBD




