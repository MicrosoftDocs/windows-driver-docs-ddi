---
UID: NF:dbgeng.IDebugSymbols.GetModuleByOffset
title: IDebugSymbols::GetModuleByOffset method
author: windows-driver-content
description: The GetModuleByOffset method searches through the target's modules for one whose memory allocation includes the specified location.
old-location: debugger\getmodulebyoffset.htm
old-project: debugger
ms.assetid: ff51d0d1-47f1-4df6-b671-d74f791d778b
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetModuleByOffset method [Windows Debugging], IDebugSymbols2 interface, dbgeng/IDebugSymbols3::GetModuleByOffset, IDebugSymbols_2f5375ce-a9f1-4e86-ab82-7f35edc716c2.xml, IDebugSymbols interface [Windows Debugging], GetModuleByOffset method, dbgeng/IDebugSymbols::GetModuleByOffset, IDebugSymbols2 interface [Windows Debugging], GetModuleByOffset method, GetModuleByOffset method [Windows Debugging], IDebugSymbols3 interface, GetModuleByOffset method [Windows Debugging], IDebugSymbols3 interface [Windows Debugging], GetModuleByOffset method, GetModuleByOffset, IDebugSymbols2::GetModuleByOffset, IDebugSymbols::GetModuleByOffset, IDebugSymbols, debugger.getmodulebyoffset, dbgeng/IDebugSymbols2::GetModuleByOffset, IDebugSymbols3::GetModuleByOffset, GetModuleByOffset method [Windows Debugging], IDebugSymbols interface
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
-	IDebugSymbols.GetModuleByOffset
-	IDebugSymbols2.GetModuleByOffset
-	IDebugSymbols3.GetModuleByOffset
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols::GetModuleByOffset method


## -description


The <b>GetModuleByOffset</b> method searches through the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">modules</a> for one whose memory allocation includes the specified location.


## -syntax


````
HRESULT GetModuleByOffset(
  [in]            ULONG64  Offset,
  [in]            ULONG    StartIndex,
  [out, optional] PULONG   Index,
  [out, optional] PULONG64 Base
);
````


## -parameters




### -param Offset [in]

Specifies a location in the target's virtual address space which is inside the desired module's memory allocation -- for example, the address of a symbol belonging to the module.


### -param StartIndex [in]

Specifies the index to start searching from.


### -param Index [out, optional]

Receives the index of the module.  If <i>Index</i> is <b>NULL</b>, this information is not returned.


### -param Base [out, optional]

Receives the location in the target's memory address space of the base of the module.  If <i>Base</i> is <b>NULL</b>, this information is not returned.


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
</table>
 




## -remarks



Starting at the specified index, this method returns the first module it finds whose memory allocation address range includes the specified location.  If the target has more than one module whose memory address range includes this location, then subsequent modules can be found by repeated calls to this method with higher values of <i>StartIndex</i>.

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547138">GetModuleByOffset2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547080">GetModuleByIndex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetModuleByOffset method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

