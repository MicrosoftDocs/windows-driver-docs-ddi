---
UID: NE:dbgmodel.LanguageKind
title: LanguageKind
author: windows-driver-content
description: 
ms.assetid: f4f112e3-1a06-441f-92ef-dff2576274ff
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: enum
ms.keywords: LanguageKind, , 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	LanguageKind
product: Windows
targetos: Windows
tech.root: debugger
---

# LanguageKind enumeration

## -description

Identifies the language of the compiland containing a given symbol.

## -enum-fields

### -field LanguageUnknown 
Indicates that the language cannot be identified

### -field LanguageC 
Indicates the C language

### -field LanguageCPP 
Indicates the C++ language
   
### -field LanguageAssembly 
Indicates the assembly language

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
