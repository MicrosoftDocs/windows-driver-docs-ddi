---
UID: NF:dbgeng.IDebugSymbols3.GetTypeIdWide
title: IDebugSymbols3::GetTypeIdWide method
author: windows-driver-content
description: The GetTypeIdWide method looks up the specified type and return its type ID.
old-location: debugger\gettypeidwide.htm
old-project: debugger
ms.assetid: 4b0f4de6-b800-4bc0-ae1d-97d877e3b91e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetTypeIdWide method [Windows Debugging], GetTypeIdWide method [Windows Debugging], IDebugSymbols3 interface, GetTypeIdWide,IDebugSymbols3.GetTypeIdWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetTypeIdWide method, IDebugSymbols3::GetTypeIdWide, dbgeng/IDebugSymbols3::GetTypeIdWide, debugger.gettypeidwide
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
-	IDebugSymbols3.GetTypeIdWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetTypeIdWide method


## -description


The <b>GetTypeIdWide</b>  method looks up the specified type and return its type ID.


## -syntax


````
HRESULT GetTypeIdWide(
  [in]  ULONG64 Module,
  [in]  PCWSTR  Name,
  [out] PULONG  TypeId
);
````


## -parameters




### -param Module [in]

Specifies the base address of the module to which the type belongs.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.  If <i>Name</i> contains a module name, <i>Module</i> is ignored. 


### -param Name [in]

Specifies the name of the type whose type ID is desired.  If <i>Name</i> is a module-qualified name (for example <b>mymodule!main</b>), the <i>Module</i> parameter is ignored.


### -param TypeId [out]

Receives the type ID of the symbol.


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



If the specified symbol is a type, these methods return the type ID for that type; otherwise, they return the type ID for the type of the symbol.

A variable whose type was defined using <b>typedef</b> has a type ID that identifies the original type, not the type created by <b>typedef</b>.  In the following example, the type ID of <b>MyInstance</b> corresponds to the name <b>MyStruct</b> (this correspondence can be seen by passing the type ID to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549408">GetTypeName</a>):

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct MyStruct { int a; };
typedef struct MyStruct MyType;
MyType MyInstance;</pre>
</td>
</tr>
</table></span></div>
Moreover, calling these methods for <b>MyStruct</b> and <b>MyType</b> yields type IDs corresponding to <b>MyStruct</b> and <b>MyType</b>, respectively.

For more information about symbols and symbol names, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549173">GetSymbolTypeId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548062">GetOffsetTypeId</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetTypeIdWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

