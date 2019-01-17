---
UID: NF:wdbgexts.GetShortField
title: GetShortField function
description: The GetShortField function reads the value of a member in a structure if its size is less than or equal to 8 bytes, or initializes a structure so it can be read later.
old-location: debugger\getshortfield.htm
tech.root: debugger
ms.assetid: f5f00e88-b758-4f37-9fe5-5db8f20835b1
ms.date: 05/03/2018
ms.keywords: GetShortField, GetShortField function [Windows Debugging], WdbgExts_Ref_ef67af78-e72f-440c-9ef3-d84b8cca12dc.xml, debugger.getshortfield, wdbgexts/GetShortField
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	GetShortField
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetShortField function


## -description


The <b>GetShortField</b> function reads the value of a member in a structure if its size is less than or equal to 8 bytes, or initializes a structure so it can be read later.  This function is not intended to be used directly; <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a> should be used instead.


## -parameters




### -param TypeAddress [in]

The meaning of this parameter depends on the value of <i>StoreAddress</i>.





#### If StoreAddress is non-zero:

Specifies the address of the structure in the target's memory.  This address is used for subsequent calls when <i>StoreAddress</i> is zero. 



#### If StoreAddress is zero:

<i>TypeAddress</i> is ignored.  The value of <i>TypeAddress</i> from the last call when <i>StoreAddress</i> was non-zero is used to specify the address of the structure in the target's memory. 


### -param Name [in]

The meaning of this parameter depends on the value of <i>StoreAddress</i>.





#### If StoreAddress is non-zero:

Specifies the name of the type of the structure at <i>TypeAddress</i>.



#### If StoreAddress is zero:

Specifies the name of the member in the structure to read.  The address and type of the structure are remembered from a previous call to this function with <i>StoreAddress</i> not equal to zero.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield". 


### -param StoreAddress [in]

Specifies the mode of this function.





#### If StoreAddress is non-zero:

Causes this function to initialize a structure for reading its members.  The address and type name for the structure is remembered.

If the bit value 0x2 is set in <i>StoreAddress</i>, the address <i>TypeAddress</i> is considered a physical address; otherwise, it is considered a virtual address. 



#### If StoreAddress is zero:

Causes this function to read a member from a previously initialized structure. 


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>If <i>StoreAddress</i> is non-zero:</b></dt>
</dl>
</td>
<td width="60%">
If the function succeeds, it returns the value zero.  If the function fails because the caller passed a zero value as <i>TypeAddress</i>, it returns the value MEMORY_READ_ERROR (defined in Wdbgexts.h).  If the function fails for any other reason, it returns an <a href="https://msdn.microsoft.com/41d64bbc-cefe-4665-b054-e6bd135ccd20">IG_DUMP_SYMBOL_INFO error code</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>If <i>StoreAddress</i> is zero:</b></dt>
</dl>
</td>
<td width="60%">
If the function succeeds, it returns the value of the specified field in the previously initialized structure.  The structure is the one initialized in a previous call to <b>GetShortField</b>.  The field is the one specified by the <i>Name</i> parameter of the current call to <b>GetShortField</b>. The return value is cast to ULONG64.  If the function fails, it returns the value zero. 

</td>
</tr>
</table>
 




## -remarks



When <b>GetShortField</b> is called with a nonzero <i>StoreAddress</i> value, it initializes the structure located at the address specified by <i>TypeAddress</i>. Only one structure can be initialized at a time. If <b>GetShortField</b> is called more than once with a nonzero <i>StoreAddress</i> value, only the structure specified in the most recent call is initialized. When <b>GetShortField</b> is called with <i>StoreAddress</i> equal to zero, it accesses the most recently initialized structure, reads in that structure the field specified by <i>Name</i>, and returns the value of that field. 

This function does not need to be called directly.  The macros <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a> call this function with <i>StoreAddress</i> non-zero to prepare a structure for reading its members.  The macro <a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a> calls this function with <i>StoreAddress</i> (and <i>TypeAddress</i>) equal to zero, to read members from the structure.

<div class="alert"><b>Note</b>    because this function stores the <i>TypeAddress</i> and <i>Name</i> by using static local variables, and because this function is defined in WdbgExts.h, the C pre-processor will create a new instance of this function for each DLL, and <i>TypeAddress</i> and <i>Name</i> will only be available within a single source file.  In other words, the structure must be initialized in the same source file from which the members are read.</div>
<div> </div>
The <b>ReadField</b> and <b>ReadFieldStr</b> macros read a field whose size is less than 8 bytes from a structure initialized with <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a>. 

<pre class="syntax" xml:space="preserve"><code>#define ReadField(Field) \
    GetShortField(0, #Field, 0)

#define ReadFieldStr(FieldStr) \
    GetShortField(0, FieldStr, 0)</code></pre>
<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>
<i>Field</i>
<i>FieldStr</i>
<h3><a id="ddk_getdebuggerdata_dbwx"></a><a id="DDK_GETDEBUGGERDATA_DBWX"></a></h3>
<h3><a id="Return_Value"></a><a id="return_value"></a><a id="RETURN_VALUE"></a>Return Value</h3>
If this macro succeeds, it returns the value of the specified field in the previously initialized structure. The structure is the one initialized in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a>, <b>InitTypeStrRead</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a>, <b>InitTypeStrReadPhysical</b>, or <b>GetShortField</b>.  The field is the one specified by the <i>Field</i> or <i>FieldStr</i> parameter of <b>ReadField</b>.  The return value is cast to ULONG64.  If the function fails, it returns the value zero. 

The parameter <i>Field</i> is the name of the member.  For <b>ReadField</b>, the C pre-processor will turn the parameter into a string.  For <b>ReadFieldStr</b>, <i>Field</i> is expected to already be an ASCII string.  For example, the following two commands are identical and read the same member from a previously initialized structure:


<ul>
<li>ReadField( myField );</li>
<li>ReadFieldStr( "myField" );</li>
</ul>


Submembers can be read by using a period-separated path, for example, "myField.mySubfield".

<div class="alert"><b>Note</b>    Because these macros use the <b>GetShortField</b> function, they must be called from the same source code file as the macros that initialize the structure for reading.  For more details, see <b>GetShortField</b>.</div>
<div> </div>
If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a> macro initializes a structure so that its members can be read using <a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a>.

<pre class="syntax" xml:space="preserve"><code>#define InitTypeRead(
    Addr,
    Type
);</code></pre>
Parameters

<i>Addr</i>

Specifies the address of the structure in the target's virtual memory.

<i>Type</i>

Specifies the name of the type of the structure.  The C pre-processor will turn <i>Type</i> into a string.

<b>Returns value</b>

If this macro succeeds, it returns the value zero.  If it fails because the caller passed a zero value as <i>Addr</i>, it returns the value MEMORY_READ_ERROR (defined in Wdbgexts.h).  If it fails for any other reason, it returns an <a href="https://msdn.microsoft.com/41d64bbc-cefe-4665-b054-e6bd135ccd20">IG_DUMP_SYMBOL_INFO error code</a>. 

The <b>InitTypeReadPhysical</b> and <b>InitTypeStrReadPhysical</b> macros initialize a structure in physical memory so that its members can be read using <a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a>.

<pre class="syntax" xml:space="preserve"><code>#define InitTypeReadPhysical(
    Addr,
    Type,
    TypeStr
);</code></pre>
Parameters

<i>Addr</i>

Specifies the address of the structure in the target's physical memory.

<i>Type</i>

Specifies the name of the type of the structure.  The C pre-processor will turn <i>Type</i> into a string.

<i>TypeStr</i>

Specifies the name of the type of the structure.  <i>TypeStr</i> is expected to be an ASCII string.

<b>Returns value</b>

If this macro succeeds, it returns the value zero.  If it fails because the caller passed a zero value as <i>Addr</i>, it returns the value MEMORY_READ_ERROR (defined in Wdbgexts.h).  If it fails for any other reason, it returns an <a href="https://msdn.microsoft.com/41d64bbc-cefe-4665-b054-e6bd135ccd20">IG_DUMP_SYMBOL_INFO error code</a>.  

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a> macro initializes a structure so that its members can be read using <a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a>.

<pre class="syntax" xml:space="preserve"><code>#define InitTypeRead(
    Addr,
    TypeStr
);</code></pre>
Parameters

<i>Addr</i>

Specifies the address of the structure in the target's virtual memory.

<i>Type</i>

Specifies the name of the type of the structure.  <i>TypeStr</i> is expected to be an ASCII string.

<b>Returns value</b>

If this macro succeeds, it returns the value zero.  If it fails because the caller passed a zero value as <i>Addr</i>, it returns the value MEMORY_READ_ERROR (defined in Wdbgexts.h).  If it fails for any other reason, it returns an <a href="https://msdn.microsoft.com/41d64bbc-cefe-4665-b054-e6bd135ccd20">IG_DUMP_SYMBOL_INFO error code</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a>
 

 

