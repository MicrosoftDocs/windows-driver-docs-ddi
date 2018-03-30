---
UID: NS:wdbgexts._SYM_DUMP_PARAM
title: "_SYM_DUMP_PARAM"
author: windows-driver-content
description: The IG_DUMP_SYMBOL_INFO Ioctl operation provides information about the type of a symbol.
old-location: debugger\ig_dump_symbol_info.htm
old-project: debugger
ms.assetid: 5a00f401-89e5-4863-ab14-a8ab7eec1869
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PSYM_DUMP_PARAM, PSYM_DUMP_PARAM, PSYM_DUMP_PARAM structure pointer [Windows Debugging], SYM_DUMP_PARAM, SYM_DUMP_PARAM structure [Windows Debugging], WdbgExts_Ref_22e264c9-ed41-4257-a192-7b3f6d4ffdea.xml, _SYM_DUMP_PARAM, debugger.ig_dump_symbol_info, wdbgexts/PSYM_DUMP_PARAM, wdbgexts/SYM_DUMP_PARAM"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	SYM_DUMP_PARAM
product: Windows
targetos: Windows
req.typenames: SYM_DUMP_PARAM, *PSYM_DUMP_PARAM
req.product: Windows 10 or later.
---

# _SYM_DUMP_PARAM structure


## -description


The IG_DUMP_SYMBOL_INFO <a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a> operation provides information about the type of a symbol.  When calling <b>Ioctl</b> with <i>IoctlType</i> set to IG_DUMP_SYMBOL_INFO, <i>IpvData</i> should contain an instance of the SYM_DUMP_PARAM structure.


## -struct-fields




### -field size

Specifies the size, in bytes, of this structure.  It should be set to <code>sizeof(SYM_DUMP_PARAM)</code>.


### -field sName

Specifies the name of the symbol to lookup.


### -field Options

Specifies the flags that determine the behavior of this <b>Ioctl</b> operation.  For a description of these flags, see Remarks.


### -field addr

Specifies the address of the symbol.


### -field listLink

Specifies the field that contains the next item in a linked list.  If the symbol is an entry in a linked list, this <b>Ioctl</b> operation can iterate over the items in the list using the field specified here as the pointer to the next item in the list.  The type of this structure is <a href="https://msdn.microsoft.com/library/windows/hardware/ff545316">FIELD_INFO</a>.

The callback function specified in the <b>fieldCallBack</b> member of this structure is called, during this <b>Ioctl</b> operation, for each item in the list.  When it is called, it is passed this <b>linkList</b> structure with the members filled in for the list entry along with the contents of the <b>Context</b> member.

DBG_DUMP_LIST should be set in <b>Options</b> to tell this <b>Ioctl</b> to iterate over the list.


### -field CallbackRoutine

Specifies a callback function that is called by the engine.  The engine provides the callback function with information about the symbol and its members.


### -field nFields

Specifies the number of entries in the <b>Fields</b> array.


### -field Fields

Specifies an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff545316">FIELD_INFO</a> structures that control the behavior of this operation for individual members of the specified symbol. See FIELD_INFO for details.


### -field ModBase

Receives the location in the target's memory of the start of the module that contains the symbol.


### -field TypeId

Receives the type ID of the symbol.


### -field TypeSize

Receives the size, in bytes, of the symbol in the target's memory.


### -field BufferSize

Specifies the size, in bytes, of the <b>pBuffer</b> buffer.


### -field fPointer

Receives a Boolean value that indicates whether the symbol is a pointer.  <b>fPointer</b> is <b>FALSE</b> if the symbol is not a pointer.  It is 1 if the symbol is a 32-bit pointer and 3 if the symbol is a 64-bit pointer.


### -field fArray

Receives a Boolean value that indicates whether the symbol is an array.  <b>fArray</b> is <b>FALSE</b> if the symbol is not an array and <b>TRUE</b> if it is.


### -field fStruct

Receives a Boolean value that indicates whether the symbol is a structure.  <b>fStruct</b> is <b>FALSE</b> if the symbol is not a structure and <b>TRUE</b> if it is.


### -field fConstant

Receives a Boolean value that indicates whether the symbol is a constant.  <b>fConstant</b> is <b>FALSE</b> if the symbol is not a constant and <b>TRUE</b> if it is.


### -field Reserved


#### - Context

Specifies a pointer that is passed to the callback function in the <b>CallbackRoutine</b> member and to the callback functions in the <b>fieldCallBack</b> member of the <b>linkList</b> and <b>Fields</b> members.


#### - pBuffer

Specifies a buffer that receives information about the symbol.  This buffer is only used if the DBG_DUMP_COPY_TYPE_DATA flag is set in <b>Options</b>.  The size of this buffer is specified in <b>BufferSize</b>.


## -remarks



The parameters for the IG_DUMP_SYMBOL_INFO <a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a> operation are the members of the SYM_DUMP_PARAM structure.

This <b>Ioctl</b> operation looks up the module information for the symbol, loading module symbols if possible.

If <b>nFields</b> is zero and DBG_DUMP_CALL_FOR_EACH is set in <b>Options</b>, the callback function specified in <b>CallbackRoutine</b> is called for every field in the symbol.

If <b>nFields</b> is non-zero and DBG_DUMP_CALL_FOR_EACH is set in <b>Options</b>, callbacks are only made for those fields matching the <b>fName</b> member of one of the <b>Fields</b> elements.  If a field matches a <b>fName</b> member and the <b>fieldCallBack</b> member is not <b>NULL</b>, the callback function in  <b>fieldCallBack</b> is called; if it is <b>NULL</b>, the callback function in <b>CallbackRoutine</b> is called instead.

<h3><a id="ddk_dbg_dump_xxx_dbx"></a><a id="DDK_DBG_DUMP_XXX_DBX"></a></h3>
The DBG_DUMP_<i>XXX</i> bit flags are used by the <b>Options</b> member of the SYM_DUMP_PARAM structure to control the behavior of the <b>IG_DUMP_SYMBOL_INFO</b><a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a> operation.

The following flags can be present.

<table>
<tr>
<th>Flag</th>
<th>Effect</th>
</tr>
<tr>
<td>
DBG_DUMP_NO_INDENT

</td>
<td>
Members are not indented in the output.

</td>
</tr>
<tr>
<td>
DBG_DUMP_NO_OFFSET

</td>
<td>
Offsets are not printed.

</td>
</tr>
<tr>
<td>
DBG_DUMP_VERBOSE

</td>
<td>
Verbose output.

</td>
</tr>
<tr>
<td>
DBG_DUMP_CALL_FOR_EACH

</td>
<td>
A callback function is called for each member.

</td>
</tr>
<tr>
<td>
DBG_DUMP_LIST

</td>
<td>
The symbol is an entry in a linked list and the IG_DUMP_SYMBOL_INFO <b>Ioctl</b> operation will iterate over this list.  The description of the member that points to the next item in the list is specified by the <b>linkList</b> member of the SYM_DUMP_PARAM structure.

</td>
</tr>
<tr>
<td>
DBG_DUMP_NO_PRINT

</td>
<td>
Nothing is printed (only callback functions are called and data copies are performed).

</td>
</tr>
<tr>
<td>
DBG_DUMP_GET_SIZE_ONLY

</td>
<td>
The <b>Ioctl</b> operation returns the size of the symbol only; it will not print member information or call callback functions.

</td>
</tr>
<tr>
<td>
DBG_DUMP_COMPACT_OUT

</td>
<td>
Newlines are not printed after each member.

</td>
</tr>
<tr>
<td>
DBG_DUMP_ARRAY

</td>
<td>
The symbol is an array.  The number of elements in the array is specified by the member <b>listLink-&gt;size</b> of the SYM_DUMP_PARAM structure.

</td>
</tr>
<tr>
<td>
DBG_DUMP_ADDRESS_OF_FIELD

</td>
<td>
The value of <b>addr</b> is actually the address of the member <b>listLink-&gt;fName</b> of the SYM_DUMP_PARAM structure and not the beginning of the symbol.

</td>
</tr>
<tr>
<td>
DBG_DUMP_ADDRESS_AT_END

</td>
<td>
The value of <b>addr</b> is actually the address at the end of the symbol and not the beginning of the symbol.

</td>
</tr>
<tr>
<td>
DBG_DUMP_COPY_TYPE_DATA

</td>
<td>
The value of the symbol is copied into the member <b>pBuffer</b>.  This can only be used for primitive types--for example, ULONG or PVOID--it cannot be used with structures.

</td>
</tr>
<tr>
<td>
DBG_DUMP_READ_PHYSICAL

</td>
<td>
The symbol's value will be read directly from the target's physical memory.

</td>
</tr>
<tr>
<td>
DBG_DUMP_FUNCTION_FORMAT

</td>
<td>
When formatting a symbol that has a function type, the function format will be used, for example,  <code>function(arg1, arg2, ...)</code>

</td>
</tr>
<tr>
<td>
DBG_DUMP_BLOCK_RECURSE

</td>
<td>
Recurse through nested structures; but do not follow pointers.

</td>
</tr>
</table>
 

In addition, the result of the macro DBG_DUMP_RECUR_LEVEL(<i>Level</i>) can be added to the bit-set to specify how deep into structures to recurse.  <i>Level</i> can be a number between 0 and 15.

<h3><a id="ddk_dbg_dump_field_xxx_dbx"></a><a id="DDK_DBG_DUMP_FIELD_XXX_DBX"></a></h3>
The DBG_DUMP_FIELD_<i>XXX</i> bit flags are used by the <b>fOptions</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545316">FIELD_INFO</a> structure to control the behavior of the <b>IG_DUMP_SYMBOL_INFO</b><a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a> operation.

The following flags can be present.

<table>
<tr>
<th>Flag</th>
<th>Effect</th>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_CALL_BEFORE_PRINT

</td>
<td>
The callback function is called before printing the member.

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_NO_CALLBACK_REQ

</td>
<td>
No callback function is called.

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_RECUR_ON_THIS

</td>
<td>
Submembers of the member are processed.

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_FULL_NAME

</td>
<td>
<b>fName</b> must match completely, as opposed to just having a matching prefix, for the member to be processed.  

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_ARRAY

</td>
<td>
Print array elements of an array member.

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_COPY_FIELD_DATA

</td>
<td>
The value of the member is copied into <b>pBuffer</b>.

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_RETURN_ADDRESS

</td>
<td>
During a callback or when <b>Ioctl</b> returns, the FIELD_INFO.<b>address</b> member contains the address of the symbol's member.

If no address is supplied for the type, FIELD_INFO.<b>address</b> contains total offset of the member from the beginning of the type.

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_SIZE_IN_BITS

</td>
<td>
For a bit field, return the offset and size in bits instead of bytes.

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_NO_PRINT

</td>
<td>
Do not print this member (only callback function are called and data copies are performed).

</td>
</tr>
<tr>
<td>
DBG_DUMP_FIELD_DEFAULT_STRING DBG_DUMP_FIELD_WCHAR_STRING DBG_DUMP_FIELD_MULTI_STRING DBG_DUMP_FIELD_GUID_STRING 

</td>
<td>
If the member is a pointer, it is printed as a string, ANSI string , WCHAR string, MULTI string, or GUID.

</td>
</tr>
</table>
 

In addition, the result of the macro DBG_DUMP_RECUR_LEVEL(<i>Level</i>) can be added to the bit-set to specify how deep into structures to recurse.  <i>Level</i> can be a number between 0 and 15.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540433">DBG_DUMP_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545316">FIELD_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550910">IG_DUMP_SYMBOL_INFO Error Codes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a>
 

 

