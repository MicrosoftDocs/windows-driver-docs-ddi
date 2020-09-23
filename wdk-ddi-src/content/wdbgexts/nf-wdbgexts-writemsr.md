---
UID: NF:wdbgexts.WriteMsr
title: WriteMsr function (wdbgexts.h)
description: The WriteMsr function writes to a Model-Specific Register (MSR).
old-location: debugger\writemsr.htm
tech.root: debugger
ms.assetid: a88c2c74-ab9a-4d9a-aeb7-d08bfe497da4
ms.date: 05/03/2018
keywords: ["WriteMsr function"]
ms.keywords: WdbgExts_Ref_faeb78e1-24a2-4210-94f9-4e468ba69181.xml, WriteMsr, WriteMsr function [Windows Debugging], dbgeng/WriteMsr, debugger.writemsr
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
 - WriteMsr
 - wdbgexts/WriteMsr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dbgeng.h
api_name:
 - WriteMsr
---

# WriteMsr function


## -description

The <b>WriteMsr</b> function writes to a Model-Specific Register (MSR).

## -parameters

### -param MsrReg 

[in]
Specifies the ID number of the MSR.

### -param MsrValue 

[in]
Specifies the new value of the MSR.

## -remarks

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.