---
UID: NF:wdbgexts.ReloadSymbols
title: ReloadSymbols function
author: windows-driver-content
description: The ReloadSymbols function deletes symbol information from the debugger so that it can be reloaded as needed. This function behaves the same way as the debugger command .reload.
old-location: debugger\reloadsymbols.htm
old-project: debugger
ms.assetid: 5778f57c-52dd-43f4-b0f7-d07e0c40512b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ReloadSymbols, ReloadSymbols function [Windows Debugging], WdbgExts_Ref_c48c63b8-6c59-42f7-8a44-78462cbf653f.xml, wdbgexts/ReloadSymbols, debugger.reloadsymbols
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	ReloadSymbols
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# ReloadSymbols function


## -description


The <b>ReloadSymbols</b> function deletes symbol information from the debugger so that it can be reloaded as needed.  This function behaves the same way as the debugger command <a href="https://msdn.microsoft.com/750eb1a2-7af9-4f2d-81ca-9ea0fb157961">.reload</a>.


## -syntax


````
__inline VOID ReloadSymbols(
  _In_opt_ PSTR Arg
);
````


## -parameters




### -param OPTIONAL

TBD




#### - Arg [in, optional]

Specifies the arguments for the debugger command <b>.reload</b>.  For example, setting <i>Arg</i> to <b>/u ntdll.dll</b> has the same effect as the command <b>.reload /u ntdll.dll</b>.


## -returns



None




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564805">.reload (Reload Module)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ReloadSymbols function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

