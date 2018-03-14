---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolRegister
title: IDebugSymbolGroup2::GetSymbolRegister method
author: windows-driver-content
description: The GetSymbolRegister method returns the register that contains the value or a pointer to the value of a symbol in a symbol group.
old-location: debugger\getsymbolregister.htm
old-project: debugger
ms.assetid: 6b95ca8c-604b-4497-9798-02f362095709
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ComOther_9383fee9-ec27-4ccb-8768-02bd550746d7.xml, GetSymbolRegister method [Windows Debugging], GetSymbolRegister method [Windows Debugging], IDebugSymbolGroup2 interface, GetSymbolRegister,IDebugSymbolGroup2.GetSymbolRegister, IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], GetSymbolRegister method, IDebugSymbolGroup2::GetSymbolRegister, dbgeng/IDebugSymbolGroup2::GetSymbolRegister, debugger.getsymbolregister
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbolGroup2.GetSymbolRegister
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2::GetSymbolRegister method


## -description


The <b>GetSymbolRegister</b> method returns the register that contains the value or a pointer to the value of a symbol in a symbol group.


## -syntax


````
HRESULT GetSymbolRegister(
  [in]  ULONG  Index,
  [out] PULONG Register
);
````


## -parameters




### -param Index [in]

The index of the symbol to return the register for. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Register [out]

The index of the register that contains the value or a pointer to the value of the symbol.


## -returns



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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The symbol's value and a pointer to it are not contained in a register, or the register is not known.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.  For more information about registers and the register index, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::GetSymbolRegister method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

