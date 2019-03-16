---
UID: NF:dbgeng.IDebugSymbols3.GetFieldTypeAndOffset
title: IDebugSymbols3::GetFieldTypeAndOffset (dbgeng.h)
description: The GetFieldTypeAndOffset method returns the type of a field and its offset within a container.
old-location: debugger\getfieldtypeandoffset.htm
tech.root: debugger
ms.assetid: a73a3bb5-f9f4-41d7-9df7-c7f36a01d157
ms.date: 05/03/2018
ms.keywords: GetFieldTypeAndOffset, GetFieldTypeAndOffset method [Windows Debugging], GetFieldTypeAndOffset method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetFieldTypeAndOffset method, IDebugSymbols3.GetFieldTypeAndOffset, IDebugSymbols3::GetFieldTypeAndOffset, IDebugSymbols_032d7936-6c9c-4748-ac81-a15673aa4e0f.xml, dbgeng/IDebugSymbols3::GetFieldTypeAndOffset, debugger.getfieldtypeandoffset
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSymbols3.GetFieldTypeAndOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetFieldTypeAndOffset


## -description


The <b>GetFieldTypeAndOffset</b>  method returns the type of a field and its offset within a container.


## -parameters




### -param Module [in]

Specifies the module containing the types of both the container and the field.


### -param ContainerTypeId [in]

Specifies the type ID for the container's type.  Examples of containers include structures, unions, and classes.


### -param Field [in]

Specifies the name of the field whose type and offset are requested.  Subfields may be specified by using a dot-separated path.


### -param FieldTypeId [out, optional]

Receives the type ID of the field.


### -param Offset [out, optional]

Receives the offset of the field <i>Field</i> from the base memory location of an instance of the container.


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
The field <i>Field</i> could not be found in the type specified by <i>ContainerTypeId</i>.

</td>
</tr>
</table>
 




## -remarks



An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the type of this field and its location relative to the location of MyStruct structure can be found by passing "MyField.MySubField" as the <i>Field</i> parameter to this method.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.  For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546758">GetFieldOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549376">GetTypeId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

