---
UID: NF:dbgeng.IDebugSymbols2.GetOffsetByLine
title: IDebugSymbols2::GetOffsetByLine method
author: windows-driver-content
description: The GetOffsetByLine method returns the location of the instruction that corresponds to a specified line in the source code.
old-location: debugger\getoffsetbyline.htm
old-project: debugger
ms.assetid: 347e0d45-8be1-4e4e-8a6a-44d5c914bf0f
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: debugger.getoffsetbyline, dbgeng/IDebugSymbols2::GetOffsetByLine, IDebugSymbols interface [Windows Debugging], GetOffsetByLine method, IDebugSymbols3 interface [Windows Debugging], GetOffsetByLine method, IDebugSymbols2::GetOffsetByLine, GetOffsetByLine, IDebugSymbols3::GetOffsetByLine, dbgeng/IDebugSymbols3::GetOffsetByLine, IDebugSymbols2 interface [Windows Debugging], GetOffsetByLine method, GetOffsetByLine method [Windows Debugging], IDebugSymbols, GetOffsetByLine method [Windows Debugging], IDebugSymbols3 interface, GetOffsetByLine method [Windows Debugging], IDebugSymbols interface, IDebugSymbols_1aa7fddc-6a33-469e-828f-45ff0f31aae7.xml, IDebugSymbols::GetOffsetByLine, IDebugSymbols2, dbgeng/IDebugSymbols::GetOffsetByLine, GetOffsetByLine method [Windows Debugging], IDebugSymbols2 interface
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
-	IDebugSymbols.GetOffsetByLine
-	IDebugSymbols2.GetOffsetByLine
-	IDebugSymbols3.GetOffsetByLine
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::GetOffsetByLine method


## -description


The <b>GetOffsetByLine</b>  method returns the location of the instruction that corresponds to a specified line in the source code.


## -syntax


````
HRESULT GetOffsetByLine(
  [in]  ULONG    Line,
  [in]  PCSTR    File,
  [out] PULONG64 Offset
);
````


## -parameters




### -param Line [in]

Specifies the line number in the source file.


### -param File [in]

Specifies the file name of the source file.


### -param Offset [out]

Receives the location in the target's virtual address space of an instruction for the specified line.


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
</table>
 




## -remarks



A line in a source file might correspond to multiple instructions and this method can return any one of these instructions.

For more information about source files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546995">GetLineByOffset</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetOffsetByLine method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

