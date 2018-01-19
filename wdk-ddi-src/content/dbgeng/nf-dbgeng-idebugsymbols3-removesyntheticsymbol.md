---
UID: NF:dbgeng.IDebugSymbols3.RemoveSyntheticSymbol
title: IDebugSymbols3::RemoveSyntheticSymbol method
author: windows-driver-content
description: The RemoveSyntheticSymbol method removes a synthetic symbol from a module in the current process.
old-location: debugger\removesyntheticsymbol.htm
old-project: debugger
ms.assetid: 07825be3-84a1-4aab-a9f0-22a45f636a04
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::RemoveSyntheticSymbol, RemoveSyntheticSymbol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols3.RemoveSyntheticSymbol
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbols3::RemoveSyntheticSymbol method



## -description
The <b>RemoveSyntheticSymbol</b> method removes a synthetic symbol from a module in the current process.



## -syntax

````
HRESULT RemoveSyntheticSymbol(
  [in] PDEBUG_MODULE_AND_ID Id
);
````


## -parameters

### -param Id [in]

Specifies the synthetic symbol to remove.  This must be the same value returned in the <i>Id</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff537943">AddSyntheticSymbol</a>.  See <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a> for details about the type of this parameter.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>No synthetic symbol was found at the specified location.  This is returned if a synthetic symbol at this location was previously removed or discarded.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
If the module containing a synthetic symbol is reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the <i>Module</i> parameter set to the name of the module - the synthetic symbol will be discarded.

For more information about synthetic symbols, see Synthetic Symbols.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537943">AddSyntheticSymbol</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554536">RemoveSyntheticModule</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::RemoveSyntheticSymbol method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

