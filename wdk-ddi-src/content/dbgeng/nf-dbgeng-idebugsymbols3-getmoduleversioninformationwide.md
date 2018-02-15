---
UID: NF:dbgeng.IDebugSymbols3.GetModuleVersionInformationWide
title: IDebugSymbols3::GetModuleVersionInformationWide method
author: windows-driver-content
description: The GetModuleVersionInformationWide method returns version information for the specified module.
old-location: debugger\getmoduleversioninformationwide.htm
old-project: debugger
ms.assetid: 60bb493c-81a2-45d7-8c2c-939afeda8a14
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.getmoduleversioninformationwide, IDebugSymbols3::GetModuleVersionInformationWide, dbgeng/IDebugSymbols3::GetModuleVersionInformationWide, GetModuleVersionInformationWide method [Windows Debugging], IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetModuleVersionInformationWide method, GetModuleVersionInformationWide, GetModuleVersionInformationWide method [Windows Debugging], IDebugSymbols3 interface
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
-	IDebugSymbols3.GetModuleVersionInformationWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols3::GetModuleVersionInformationWide method


## -description


The <b>GetModuleVersionInformationWide</b>  method returns version information for the specified module.


## -syntax


````
HRESULT GetModuleVersionInformationWide(
  [in]            ULONG   Index,
  [in]            ULONG64 Base,
  [in]            PCWSTR  Item,
  [out, optional] PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  VerInfoSize
);
````


## -parameters




### -param Index [in]

Specifies the index of the module.  If it is set to DEBUG_ANY_ID, the <i>Base</i> parameter is used to specify the location of the module instead.


### -param Base [in]

If <i>Index</i> is DEBUG_ANY_ID, specifies the location in the target's memory address space of the base of the module.  Otherwise it is ignored.


### -param Item [in]

Specifies the version information being requested.  This string corresponds to the <i>lpSubBlock</i> parameter of the function <b>VerQueryValue</b>.  For details on the <b>VerQueryValue</b> function, see the Platform SDK.


### -param Buffer [out, optional]

Receives the requested version information.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size in characters of the buffer <i>Buffer</i>.


### -param VerInfoSize [out, optional]

Receives the size in characters of the version information.  If <i>VerInfoSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The size of the buffer was smaller than the size of the version information.  In this case the buffer is filled with the truncated version information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The specified module was not found.

</td>
</tr>
</table>
 




## -remarks



Module version information is available only for loaded modules and may not be available in all sessions.

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547927">GetNumberModules</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547138">GetModuleByOffset2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547080">GetModuleByIndex</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetModuleVersionInformationWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

