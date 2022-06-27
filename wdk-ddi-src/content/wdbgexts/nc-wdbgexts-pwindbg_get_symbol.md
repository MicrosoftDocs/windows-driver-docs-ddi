---
UID: NC:wdbgexts.PWINDBG_GET_SYMBOL
title: PWINDBG_GET_SYMBOL (wdbgexts.h)
description: The PWINDBG_GET_SYMBOL (GetSymbol) function locates the symbol nearest to address.
old-location: debugger\getsymbol.htm
tech.root: debugger
ms.date: 05/27/2022
keywords: ["PWINDBG_GET_SYMBOL callback function"]
ms.keywords: GetSymbol, GetSymbol callback function [Windows Debugging], PWINDBG_GET_SYMBOL, PWINDBG_GET_SYMBOL callback, WdbgExts_Ref_a892aa24-d1ee-43f4-8fd5-ea8d00aa678a.xml, debugger.getsymbol, wdbgexts/GetSymbol
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PWINDBG_GET_SYMBOL
 - wdbgexts/PWINDBG_GET_SYMBOL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdbgexts.h
api_name:
 - PWINDBG_GET_SYMBOL
---

# PWINDBG_GET_SYMBOL callback function


## -description

The <b>PWINDBG_GET_SYMBOL</b>  (<b>GetSymbol</b>) function locates the symbol nearest to <i>address</i>.

## -parameters

### -param offset

Specifies an address near the symbol you want located.

### -param pchBuffer

Receives the name of the symbol found. This buffer must be at least 256 characters in length. 

### -param pDisplacement

Specifies the displacement from the beginning of the symbol.

