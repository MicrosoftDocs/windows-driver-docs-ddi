---
UID: NF:winspool.EnumJobNamedProperties
title: EnumJobNamedProperties function (winspool.h)
description: This topic describes the EnumJobNamedProperties function.
tech.root: print
ms.date: 04/20/2022
keywords: ["EnumJobNamedProperties function"]
ms.keywords: EnumJobNamedProperties, EnumJobNamedProperties function [Print Devices], print.enumjobnamedproperties, winspool/EnumJobNamedProperties
req.header: winspool.h
req.include-header: Winspool.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EnumJobNamedProperties
 - winspool/EnumJobNamedProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winspool.h
api_name:
 - EnumJobNamedProperties
---

## -description

This topic describes the **EnumJobNamedProperties** function.

## -parameters

### -param hPrinter [in]

Defines the **HANDLE** parameter *hPrinter*.

### -param JobId [in]

Defines the **DWORD** parameter *JobId*.

### -param pcProperties [out]

Defines the **DWORD** parameter *pcProperties*.

### -param ppProperties [out]

Defines the **PrintNamedProperty** parameter *ppProperties*.

## -returns

Returns a **DWORD** containing the number of named properties.
