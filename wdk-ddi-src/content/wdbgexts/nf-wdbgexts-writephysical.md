---
UID: NF:wdbgexts.WritePhysical
title: WritePhysical function (wdbgexts.h)
description: The WritePhysical function writes to physical memory.
old-location: debugger\writephysical.htm
tech.root: debugger
ms.assetid: faafaf0a-29ef-43ef-9f9a-f3b545e83f65
ms.date: 05/03/2018
keywords: ["WritePhysical function"]
ms.keywords: WdbgExts_Ref_4c6663a7-4fbf-4d4a-9c86-cfa51218a470.xml, WritePhysical, WritePhysical function [Windows Debugging], dbgeng/WritePhysical, debugger.writephysical
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
 - WritePhysical
 - wdbgexts/WritePhysical
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dbgeng.h
api_name:
 - WritePhysical
---

# WritePhysical function


## -description

The <b>WritePhysical</b> function writes to physical memory.

## -parameters

### -param address 

[in]
Specifies the physical address to write.

### -param buf 

[in]
Specifies the address of an array of bytes to hold the data that is written.

### -param size 

[in]
Specifies the number of bytes to write.

### -param sizew 

[out, optional]
Receives the number of bytes actually written.

## -remarks

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.

