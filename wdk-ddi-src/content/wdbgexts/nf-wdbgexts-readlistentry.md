---
UID: NF:wdbgexts.ReadListEntry
title: ReadListEntry function (wdbgexts.h)
description: The ReadListEntry function reads a doubly-linked list entry from the target's memory.
old-location: debugger\readlistentry.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ReadListEntry function"]
ms.keywords: ReadListEntry, ReadListEntry function [Windows Debugging], WdbgExts_Ref_ab7a48d6-aa2a-4ed1-a4dc-7339993ccb45.xml, debugger.readlistentry, wdbgexts/ReadListEntry
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h, Winnt.h, Ntdef.h
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
 - ReadListEntry
 - wdbgexts/ReadListEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - ReadListEntry
---

# ReadListEntry function


## -description

The <b>ReadListEntry</b> function reads a doubly-linked list entry from the target's memory.

## -parameters

### -param Address

Specifies the address of the list entry in the target.  If the target uses 32-bit pointers, this should be the address of a LIST_ENTRY32 structure.  If the target uses 64-bit pointers, this should be the address of a LIST_ENTRY64 structure.

### -param List

Receives a LIST_ENTRY64 structure that contains pointers to the previous and next entries in the list.  If the target uses 32-bit pointers, they are sign-extended to 64 bits.

## -returns

If the function succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

## -remarks

For more information about the LIST_ENTRY structures, see the Windows Driver Kit (WDK) documentation.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details).


LIST_ENTRY64 and LIST_ENTRY32 are defined in <b>winnt.h</b>.
