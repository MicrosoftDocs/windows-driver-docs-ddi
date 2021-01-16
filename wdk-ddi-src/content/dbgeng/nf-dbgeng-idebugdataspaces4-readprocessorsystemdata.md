---
UID: NF:dbgeng.IDebugDataSpaces4.ReadProcessorSystemData
title: IDebugDataSpaces4::ReadProcessorSystemData (dbgeng.h)
description: The ReadProcessorSystemData method returns data about the specified processor.
old-location: debugger\readprocessorsystemdata.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces4::ReadProcessorSystemData"]
ms.keywords: IDebugDataSpaces interface [Windows Debugging],ReadProcessorSystemData method, IDebugDataSpaces2 interface [Windows Debugging],ReadProcessorSystemData method, IDebugDataSpaces2::ReadProcessorSystemData, IDebugDataSpaces3 interface [Windows Debugging],ReadProcessorSystemData method, IDebugDataSpaces3::ReadProcessorSystemData, IDebugDataSpaces4 interface [Windows Debugging],ReadProcessorSystemData method, IDebugDataSpaces4.ReadProcessorSystemData, IDebugDataSpaces4::ReadProcessorSystemData, IDebugDataSpaces::ReadProcessorSystemData, IDebugDataSpaces_a2ffd54a-03f2-4b74-928c-b043bfdac073.xml, ReadProcessorSystemData, ReadProcessorSystemData method [Windows Debugging], ReadProcessorSystemData method [Windows Debugging],IDebugDataSpaces interface, ReadProcessorSystemData method [Windows Debugging],IDebugDataSpaces2 interface, ReadProcessorSystemData method [Windows Debugging],IDebugDataSpaces3 interface, ReadProcessorSystemData method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::ReadProcessorSystemData, dbgeng/IDebugDataSpaces3::ReadProcessorSystemData, dbgeng/IDebugDataSpaces4::ReadProcessorSystemData, dbgeng/IDebugDataSpaces::ReadProcessorSystemData, debugger.readprocessorsystemdata
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugDataSpaces4::ReadProcessorSystemData
 - dbgeng/IDebugDataSpaces4::ReadProcessorSystemData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces4::ReadProcessorSystemData
---

# IDebugDataSpaces4::ReadProcessorSystemData


## -description

The <b>ReadProcessorSystemData</b> method returns data about the specified processor.

## -parameters

### -param Processor 

[in]
Specifies the processor whose data is to be read.

### -param Index 

[in]
Specifies the data type to read.  The following table contains the valid values.  After successful completion, the data returned in the buffer <i>Buffer</i> has the type specified by the middle column.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_DATA_KPCR_OFFSET

</td>
<td>
Returns the virtual address of the processor's Processor Control Region (PCR).

In this case, the argument <i>Buffer</i> can be considered to have type PULONG64.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KPRCB_OFFSET

</td>
<td>
Returns the virtual address of the processor's Processor Control Block (PRCB).

In this case, the argument <i>Buffer</i> can be considered to have type PULONG64.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KTHREAD_OFFSET

</td>
<td>
Returns the virtual address of the KTHREAD structure for the system thread  running on the processor.

In this case, the argument <i>Buffer</i> can be considered to have type PULONG64.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_BASE_TRANSLATION_VIRTUAL_OFFSET

</td>
<td>
Returns the virtual address of the base of the paging information owned by the operating system or the processor.  The address and the content at the address are processor- and operating-system-dependent. 

In this case, the argument <i>Buffer</i> can be considered to have type PULONG64.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_PROCESSOR_IDENTIFICATION

</td>
<td>
Returns a description of the processor.

In this case, the argument <i>Buffer</i> can be considered to have type PDEBUG_PROCESSOR_IDENTIFICATION_ALL .

</td>
</tr>
<tr>
<td>
DEBUG_DATA_PROCESSOR_SPEED

</td>
<td>
Returns the speed of the processor in MHz.  This may not work in a particular session.

In this case, the argument <i>Buffer</i> can be considered to have type PULONG.

</td>
</tr>
</table>

### -param Buffer 

[out]
Receives the processor data.  Upon successful completion of the method, the contents of this buffer may be accessed by casting <i>Buffer</i> to the type specified in the above table.

### -param BufferSize 

[in]
Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be returned.

### -param DataSize 

[out, optional]
Receives the size of the data in bytes.  If <i>DataSize</i> is <b>NULL</b>, this information is not returned.

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
</table>
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method is only available in kernel-mode debugging.

For information about the PCR, PRCB, and KTHREAD structures, as well as information about paging tables, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.

