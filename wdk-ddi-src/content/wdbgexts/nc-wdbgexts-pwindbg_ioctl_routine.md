---
UID: NC:wdbgexts.PWINDBG_IOCTL_ROUTINE
title: PWINDBG_IOCTL_ROUTINE (wdbgexts.h)
description: The PWINDBG_IOCTL_ROUTINE (Ioctl) function performs a variety of different operations. Much of its functionality mirrors the functionality of other functions in wdbgexts.h.
old-location: debugger\ioctl.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["PWINDBG_IOCTL_ROUTINE callback function"]
ms.keywords: Ioctl, Ioctl callback function [Windows Debugging], PWINDBG_IOCTL_ROUTINE, PWINDBG_IOCTL_ROUTINE callback, WdbgExts_Ref_fa1f5367-924d-478c-a3cb-ca08bf8dde2f.xml, debugger.ioctl, wdbgexts/Ioctl
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PWINDBG_IOCTL_ROUTINE
 - wdbgexts/PWINDBG_IOCTL_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdbgexts.h
api_name:
 - PWINDBG_IOCTL_ROUTINE
---

# PWINDBG_IOCTL_ROUTINE callback function


## -description

The <b>PWINDBG_IOCTL_ROUTINE</b> (<b>Ioctl</b>) function performs a variety of different operations. Much of its functionality mirrors the functionality of other functions in wdbgexts.h.

## -parameters

### -param IoctlType

Specifies which <b>Ioctl</b> operation to perform. For a list of possible <i>IoctlType</i> values, see the "Remarks" section.

### -param lpvData

Points to the address of a data structure. The type of structure that is required depends on the value of <i>IoctlType</i>.

### -param cbSize

#### - cbSizeOfContext

Specifies the size of the structure that <i>lpvData</i> points to.

## -returns

The meaning of return value depends on <i>IoctlType</i>.  See the page for the corresponding <b>Ioctl</b> operation for the meaning of the return value.

## -remarks

The <b>Ioctl</b> function is the entry point for many of the functionalities supplied for WdbgExts extensions. Many of the other functions in wdbgexts.h are simply wrappers for calls to <b>Ioctl</b>.

The following table lists the possible <i>IoctlType</i> values.  If the <i>IoctlType</i> corresponds to another function, that function is provided; otherwise, a link to the page describing the <b>Ioctl</b> operation is provided.

<table>
<tr>
<th><i>IoctlType</i> constant</th>
<th>Equivalent function</th>
<th>lpData structure</th>
</tr>
<tr>
<td>
IG_KD_CONTEXT

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getkdcontext">GetKdContext</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_CONTROL_SPACE

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readcontrolspace">ReadControlSpace</a>


<b>ReadControlSpace64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_CONTROL_SPACE

</td>
<td>
<b>WriteControlSpace </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_IO_SPACE

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readiospace">ReadIoSpace</a>


<b>ReadIoSpace64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_IO_SPACE

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writeiospace">WriteIoSpace</a>


<b>WriteIoSpace64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_PHYSICAL

</td>
<td>

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readphysical">ReadPhysical</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_PHYSICAL

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writephysical">WritePhysical</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_IO_SPACE_EX

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readiospaceex">ReadIoSpaceEx</a>


<b>ReadIoSpaceEx64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_IO_SPACE_EX

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writeiospaceex">WriteIoSpaceEx</a>


<b>WriteIoSpaceEx64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_SET_THREAD

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-setthreadforoperation">SetThreadForOperation</a>


<b>SetThreadForOperation64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_MSR

</td>
<td>

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readmsr">ReadMsr</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_MSR

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writemsr">WriteMsr</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_DEBUGGER_DATA

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getdebuggerdata">GetDebuggerData</a>


</td>
<td></td>
</tr>
<tr>
<td>

IG_GET_KERNEL_VERSION

</td>
<td></td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_dbgkd_get_version64">DBGKD_GET_VERSION64</a>


</td>
</tr>
<tr>
<td>
IG_RELOAD_SYMBOLS

</td>
<td>
<b>ReloadSymbols </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_SET_SYMPATH

</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-getsetsympath">GetSetSympath</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_EXCEPTION_RECORD

</td>
<td>


</td>
<td></td>
</tr>
<tr>
<td>
IG_IS_PTR64

</td>
<td>
<b>IsPtr64 </b>

</td>
<td></td>
</tr>
<tr>
<td>

IG_GET_BUS_DATA

</td>
<td></td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_getsetbusdata">GETSETBUSDATA</a>


</td>
</tr>
<tr>
<td>

IG_SET_BUS_DATA

</td>
<td></td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_getsetbusdata">GETSETBUSDATA</a>


</td>
</tr>
<tr>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_sym_dump_param">IG_DUMP_SYMBOL_INFO</a>


</td>
<td></td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_sym_dump_param">SYM_DUMP_PARAM</a>


</td>
</tr>
<tr>
<td>

IG_LOWMEM_CHECK

</td>
<td></td>
<td>
See Remarks.

</td>
</tr>
<tr>
<td>
IG_SEARCH_MEMORY

</td>
<td>
<b>SearchMemory </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_CURRENT_THREAD

</td>
<td>
<b>GetCurrentThreadAddr </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_CURRENT_PROCESS

</td>
<td>
<b>GetCurrentProcessAddr </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_TYPE_SIZE

</td>
<td>
<b>GetTypeSize </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_CURRENT_PROCESS_HANDLE

</td>
<td>
<b>GetCurrentProcessHandle </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_INPUT_LINE

</td>
<td>
<b>GetInputLine </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_EXPRESSION_EX

</td>
<td>
<b>GetExpressionEx </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_TRANSLATE_VIRTUAL_TO_PHYSICAL

</td>
<td>
<b>TranslateVirtualToPhysical </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_CACHE_SIZE

</td>
<td>
<b>GetDebuggerCacheSize </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_PHYSICAL_WITH_FLAGS

</td>
<td>
<b>ReadPhysicalWithFlags </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_PHYSICAL_WITH_FLAGS

</td>
<td>
<b>WritePhysicalWithFlags </b>

</td>
<td></td>
</tr>
<tr>
<td>

IG_POINTER_SEARCH_PHYSICAL

</td>
<td></td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_pointer_search_physical">POINTER_SEARCH_PHYSICAL</a>


</td>
</tr>
<tr>
<td>

IG_GET_THREAD_OS_INFO

</td>
<td>


</td>
<td>

<a href="/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_wdbgexts_thread_os_info">WDBGEXTS_THREAD_OS_INFO</a>


</td>
</tr>
<tr>
<td>
IG_GET_CLR_DATA_INTERFACE

</td>
<td></td>
<td></td>
</tr>
<tr>
<td>
IG_GET_TEB_ADDRESS

</td>
<td>
<b>GetTebAddress </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_PEB_ADDRESS

</td>
<td>
<b>GetPebAddress </b>

</td>
<td></td>
</tr>
</table>
 

The IG_LOWMEM_CHECK <b>Ioctl</b> operation looks for memory corruption in the low 4 GB of memory.

This <b>Ioctl</b> operation does not take any parameters and the <i>lpvData</i> and <i>cbSizeOfContext</i> parameters should be set to <b>NULL</b> and zero respectively.

<h3><a id="Return_Value"></a><a id="return_value"></a><a id="RETURN_VALUE"></a>Return Value</h3>
If no corrupt memory was found, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

This operation is only available in kernel-mode debugging, and is only useful when the kernel was started using the <b>/nolowmem</b> option.

When the kernel is started with the <b>/nolowmem</b> option, the kernel, drivers, operating system, and applications are loaded in memory above 4 GB, while the low 4 GB of memory is filled with a unique pattern. The IG_LOWMEM_CHECK <b>Ioctl</b> operation checks this pattern for corruption.

This can be used to verify that a driver works correctly when using physical addresses greater than 32 bits in length. See <i>Physical Address Extension (PAE)</i>, <b>/pae</b>,  and <b>/nolowmem</b> in the Windows Driver Kit.

