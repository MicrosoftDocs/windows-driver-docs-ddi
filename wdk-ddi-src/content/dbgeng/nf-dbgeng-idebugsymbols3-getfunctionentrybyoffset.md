---
UID: NF:dbgeng.IDebugSymbols3.GetFunctionEntryByOffset
title: IDebugSymbols3::GetFunctionEntryByOffset method
author: windows-driver-content
description: The GetFunctionEntryByOffset method returns the function entry information for a function.
old-location: debugger\getfunctionentrybyoffset.htm
old-project: debugger
ms.assetid: 6b1fa9fc-f033-4d93-a2ec-f31159d6a69d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbols3::GetFunctionEntryByOffset, IDebugSymbols_2f48c855-76e5-421c-8890-9a96a0468783.xml, IDebugSymbols3, GetFunctionEntryByOffset method [Windows Debugging], IDebugSymbols3 interface, GetFunctionEntryByOffset, IDebugSymbols3 interface [Windows Debugging], GetFunctionEntryByOffset method, GetFunctionEntryByOffset method [Windows Debugging], debugger.getfunctionentrybyoffset, dbgeng/IDebugSymbols3::GetFunctionEntryByOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Winnt.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSymbols3.GetFunctionEntryByOffset
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugSymbols3::GetFunctionEntryByOffset method


## -description


The <b>GetFunctionEntryByOffset</b> method returns the function entry information for a function.


## -syntax


````
HRESULT GetFunctionEntryByOffset(
  [in]            ULONG64 Offset,
  [in]            ULONG   Flags,
  [out, optional] PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BufferNeeded
);
````


## -parameters




### -param Offset [in]

Specifies a location in the current process's virtual address space of the function's implementation.  This is the value returned in the <i>Offset</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a> and <a href="https://msdn.microsoft.com/da3ddebc-109e-43fb-a0e9-fd89d90dbbc7">IDebugSymbolGroup::GetSymbolOffset</a>, and the value of the <b>Offset</b> field in the <a href="..\dbgeng\ns-dbgeng-_debug_symbol_entry.md">DEBUG_SYMBOL_ENTRY</a> structure.


### -param Flags [in]

Specifies a bit-flag which alters the behavior of this method.  If the bit DEBUG_GETFNENT_RAW_ENTRY_ONLY is not set, the engine will provide artificial entries for well known cases.  If this bit is set the artificial entries are not used.


### -param Buffer [out, optional]

Receives the function entry information.  If the effective processor is an x86, this is the FPO_DATA structure for the function.  For all other architectures, this is the IMAGE_FUNCTION_ENTRY structure for that architecture.


### -param BufferSize [in]

Specifies the size of the buffer <i>Buffer</i>.


### -param BufferNeeded [out, optional]

Specifies the size of the function entry information.


## -returns


This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful, but the buffer was not large enough to hold the function entry information and so the information was truncated to fit.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No function entry information was found for the location <i>Offset</i>.

</td>
</tr>
</table> 



## -remarks


The structures FPO_DATA and IMAGE_FUNCTION_ENTRY are documented in "Image Help Library" which is included in Debugging Tools For Windows in the DbgHelp.chm file. 
<div class="alert"><b>Note</b>  The functions in "Image Help Library" and "Debug Help Library", documented in DbgHelp.chm, should not be called by any extension or debugger engine application.</div><div> </div>For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a>

<a href="https://msdn.microsoft.com/da3ddebc-109e-43fb-a0e9-fd89d90dbbc7">IDebugSymbolGroup::GetSymbolOffset</a>

<a href="..\dbgeng\ns-dbgeng-_debug_symbol_entry.md">DEBUG_SYMBOL_ENTRY</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetFunctionEntryByOffset method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

