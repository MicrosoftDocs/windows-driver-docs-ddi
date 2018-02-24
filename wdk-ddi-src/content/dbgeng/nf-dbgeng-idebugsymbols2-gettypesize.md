---
UID: NF:dbgeng.IDebugSymbols2.GetTypeSize
title: IDebugSymbols2::GetTypeSize method
author: windows-driver-content
description: The GetTypeSize method returns the number of bytes of memory an instance of the specified type requires.
old-location: debugger\gettypesize2.htm
old-project: Debugger
ms.assetid: b6f03eb5-e386-4e88-a729-db08f1fa460c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugSymbols interface [Windows Debugging], GetTypeSize method, debugger.gettypesize2, IDebugSymbols2::GetTypeSize, GetTypeSize method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols::GetTypeSize, GetTypeSize method [Windows Debugging], IDebugSymbols interface, IDebugSymbols3::GetTypeSize, GetTypeSize, IDebugSymbols_d1c65bea-0479-4ca8-bdfa-6c7a7376792a.xml, GetTypeSize method [Windows Debugging], IDebugSymbols3 interface [Windows Debugging], GetTypeSize method, IDebugSymbols2, dbgeng/IDebugSymbols2::GetTypeSize, IDebugSymbols2 interface [Windows Debugging], GetTypeSize method, dbgeng/IDebugSymbols3::GetTypeSize, IDebugSymbols, dbgeng/IDebugSymbols::GetTypeSize, GetTypeSize method [Windows Debugging], IDebugSymbols2 interface
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
-	IDebugSymbols.GetTypeSize
-	IDebugSymbols2.GetTypeSize
-	IDebugSymbols3.GetTypeSize
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::GetTypeSize method


## -description


The <b>GetTypeSize</b> method returns the number of bytes of memory an instance of the specified type requires.


## -syntax


````
HRESULT GetTypeSize(
  [in]  ULONG64 Module,
  [in]  ULONG   TypeId,
  [out] PULONG  Size
);
````


## -parameters




### -param Module [in]

Specifies the base address of the module containing the type.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.


### -param TypeId [in]

Specifies the type ID of the type.


### -param Size [out]

Receives the number of bytes of memory an instance of the specified type requires.


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
The method was successful

</td>
</tr>
</table>
 




## -remarks



For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549408">GetTypeName</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols::GetTypeSize method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

