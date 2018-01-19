---
UID: NF:dbgeng.IDebugSymbols3.GetModuleByModuleNameWide
title: IDebugSymbols3::GetModuleByModuleNameWide method
author: windows-driver-content
description: The GetModuleByModuleNameWide method searches through the target's modules for one with the specified name.
old-location: debugger\getmodulebymodulenamewide.htm
old-project: debugger
ms.assetid: 66ec7c51-3d2c-4a25-a356-4df06ee1b1f5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetModuleByModuleNameWide, GetModuleByModuleNameWide
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
req.alt-api: IDebugSymbols3.GetModuleByModuleNameWide
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

# IDebugSymbols3::GetModuleByModuleNameWide method



## -description
The <b>GetModuleByModuleNameWide</b>  method searches through the target's <a href="debugger.modules#modules#modules">modules</a> for one with the specified name.



## -syntax

````
HRESULT GetModuleByModuleNameWide(
  [in]            PCWSTR   Name,
  [in]            ULONG    StartIndex,
  [out, optional] PULONG   Index,
  [out, optional] PULONG64 Base
);
````


## -parameters

### -param Name [in]

Specifies the name of the desired module.


### -param StartIndex [in]

Specifies the index to start searching from.


### -param Index [out, optional]

Receives the index of the first module with the name <i>Name</i>.  If <i>Index</i> is <b>NULL</b>, this information is not returned.


### -param Base [out, optional]

Receives the location in the target's memory address space of the base of the module.  If <i>Base</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>One of the arguments passed in was invalid.

 


## -remarks
Starting at the specified index, these methods return the first module they find with the specified name.  If the target has more than one module with this name, then subsequent modules can be found by repeated calls to these methods with higher values of <i>StartIndex</i>.  

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547102">GetModuleByModuleName2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetModuleByModuleNameWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

