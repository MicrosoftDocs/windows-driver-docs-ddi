---
UID: NC:dbgeng.PDEBUG_EXTENSION_KNOWN_STRUCT
title: PDEBUG_EXTENSION_KNOWN_STRUCT (dbgeng.h)
description: The engine calls the KnownStructOutput callback function to request information about structures that the extension DLL can format for printing. The engine calls this function for the following reasons.
old-location: debugger\knownstructoutput.htm
tech.root: debugger
ms.assetid: 76b7e097-4953-4988-8999-07bbfbd65912
ms.date: 05/03/2018
keywords: ["PDEBUG_EXTENSION_KNOWN_STRUCT callback function"]
ms.keywords: Extensions_Ref_dfff8fda-36a7-42ab-9ad7-1698c352c028.xml, KnownStructOutput, KnownStructOutput callback function [Windows Debugging], PDEBUG_EXTENSION_KNOWN_STRUCT, PDEBUG_EXTENSION_KNOWN_STRUCT callback, dbgeng/KnownStructOutput, debugger.knownstructoutput
f1_keywords:
 - "dbgeng/KnownStructOutput"
 - "KnownStructOutput"
req.header: dbgeng.h
req.include-header: 
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
- UserDefined
api_location:
- dbgeng.h
api_name:
- KnownStructOutput
product:
- Windows
targetos: Windows
req.typenames: 
---

# PDEBUG_EXTENSION_KNOWN_STRUCT callback function


## -description


The engine calls the <i>KnownStructOutput</i> callback function to request information about structures that the extension DLL can format for printing. The engine calls this function for the following reasons.
<ul>
<li>Get a list of structures that the DLL can format for printing.</li>
<li>Get a single-line representation of a particular structure.</li>
<li>Ask whether a particular structure should have its name printed along with its single-line representation.</li>
</ul><div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_EXTENSION_KNOWN_STRUCT KnownStructOutput;</pre>
</td>
</tr>
</table></span></div>

## -parameters




### -param Flags [in]

One of the following values, depending on what information the engine wants to obtain from the extension DLL.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_KNOWN_STRUCT_GET_NAMES

</td>
<td>
Get a list of structure names.

</td>
</tr>
<tr>
<td>
DEBUG_KNOWN_STRUCT_SUPPRESS_TYPE_NAME

</td>
<td>
Ask whether a structure should have its  name printed.

</td>
</tr>
<tr>
<td>
DEBUG_KNOWN_STRUCT_GET_SINGLE_LINE_OUTPUT

</td>
<td>
Get  a single-line representation of a structure.

</td>
</tr>
</table>
 


### -param Offset [in]

<b>When getting a list of names:</b> Unused.

<b>When asking whether a name should be printed:</b> Unused.

<b>When getting a single-line representation:</b>  Specifies the location in the target's memory address space of the structure to be printed.


### -param TypeName [in]

<b>When getting a list of names:</b>  Unused.

<b>When asking whether a name should be printed:</b> Specifies the name of the structure.  This is one of the names returned from the DEBUG_KNOWN_STRUCT_GET_NAMES query.

<b>When getting a single-line representation:</b>  Specifies the name of the structure.  This is one of the names returned from the DEBUG_KNOWN_STRUCT_GET_NAMES query.


### -param Buffer [out]

<b>When getting a list of names:</b>  Receives a list of the names of the structures that the extension can format for printing.  One null character must appear between each pair of names.  The list must be terminated with two null characters. The number of characters written to this buffer must not exceed the value of <i>BufferSize</i>.

<b>When asking whether a name should be printed:</b> Unused.

<b>When getting a single-line representation:</b>  Receives a representation  of the structure, identified by <i>StructName</i> and <i>Address</i>, as a string. The number of characters written to this buffer must not exceed the value of <i>BufferSize</i>.


### -param BufferChars [in, out]

<b>When getting a list of names:</b>  On input, specifies the size, in characters, of  <i>Buffer</i>. On output, if the buffer is too small, receives the required buffer size.

<b>When asking whether a name should be printed:</b> Unused.

<b>When getting a single-line representation:</b>  On input, specifies the size, in characters, of <i>Buffer</i>. On output, if the buffer is too small, receives the required buffer size.


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
<b>When getting a list of names:</b><i> Buffer</i> contains the requested list of names.

<b>When asking whether a name should be printed:</b>  The printing of the name should be suppressed. That is, the name should not be printed.   

<b>When getting a single-line representation:</b><i> Buffer</i> contains the requested single-line representation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
<b>When getting a list of names:</b><i> BufferSize</i> was too small on input. On output, <i> BufferSize</i> contains the required buffer size.

<b>When asking whether a name should be printed:</b>  The printing of the name should not be suppressed. That is, the name should be printed.   

<b>When getting a single-line representation:</b><i> BufferSize</i> was too small on input. On output, <i> BufferSize</i> contains the required buffer size.

</td>
</tr>
</table>
 

All other return values indicate that the function failed.  The engine will continue ignoring the contents of <i>Buffer</i>.




## -remarks



This function is optional.  An extension DLL only needs to export <b>KnownStructOutput</b> if it has the ability to format special structures for printing on a single line.  The engine looks for this function by name in the extension DLL.

After initializing the extension DLL, the engine calls this function to query the DLL for the list of structure names it knows how to print.  Then, whenever the engine prints a summary of one of the structures whose name is in the list, it calls this function to format the structure for printing.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_known_struct">KnownStructOutput</a> is called <b>PDEBUG_EXTENSION_KNOWN_STRUCT</b>   in the Dbgeng.h header file.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_initialize">DebugExtensionInitialize</a>
 

 

