---
UID: NF:dbgeng.IDebugSymbols3.GetFieldOffset
title: IDebugSymbols3::GetFieldOffset method
author: windows-driver-content
description: The GetFieldOffset method returns the offset of a field from the base address of an instance of a type.
old-location: debugger\getfieldoffset2.htm
old-project: debugger
ms.assetid: 4081ddf9-673d-4df6-8698-726a70d32c03
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbols::GetFieldOffset, IDebugSymbols3 interface [Windows Debugging], GetFieldOffset method, IDebugSymbols2::GetFieldOffset, IDebugSymbols3::GetFieldOffset, GetFieldOffset method [Windows Debugging], IDebugSymbols interface, IDebugSymbols2 interface [Windows Debugging], GetFieldOffset method, GetFieldOffset method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging], GetFieldOffset method, GetFieldOffset method [Windows Debugging], dbgeng/IDebugSymbols2::GetFieldOffset, IDebugSymbols_3e5be57a-3af9-4fe3-a7cc-4f31fb9b54f0.xml, GetFieldOffset, GetFieldOffset method [Windows Debugging], IDebugSymbols2 interface, debugger.getfieldoffset2, dbgeng/IDebugSymbols3::GetFieldOffset, IDebugSymbols2, IDebugSymbols, dbgeng/IDebugSymbols::GetFieldOffset, IDebugSymbols3
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
-	IDebugSymbols.GetFieldOffset
-	IDebugSymbols2.GetFieldOffset
-	IDebugSymbols3.GetFieldOffset
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols3::GetFieldOffset method


## -description


The <b>GetFieldOffset</b>  method returns the offset of a field from the base address of an instance of a type.


## -syntax


````
HRESULT GetFieldOffset(
  [in]  ULONG64 Module,
  [in]  ULONG   TypeId,
  [in]  PCSTR   Field,
  [out] PULONG  Offset
);
````


## -parameters




### -param Module [in]

Specifies the module containing the types of both the container and the field.


### -param TypeId [in]

Specifies the type ID of the type containing the field.


### -param Field [in]

Specifies the name of the field whose offset is requested.  Subfields may be specified by using a dot-separated path.


### -param Offset [out]

Receives the offset of the specified field from the base memory location of an instance of the type. 


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The field <i>Field</i> could not be found in the type specified by <i>TypeId</i>.

</td>
</tr>
</table>
 




## -remarks



An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the location of this field relative to the location of MyStruct structure can be found by setting the <i>Field</i> parameter to "MyField.MySubField".

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.



