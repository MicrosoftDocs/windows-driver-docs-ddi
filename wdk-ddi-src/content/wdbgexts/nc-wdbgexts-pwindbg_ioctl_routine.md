---
UID: NC:wdbgexts.PWINDBG_IOCTL_ROUTINE
title: PWINDBG_IOCTL_ROUTINE
author: windows-driver-content
description: The PWINDBG_IOCTL_ROUTINE (Ioctl) function performs a variety of different operations. Much of its functionality mirrors the functionality of other functions in wdbgexts.h.
old-location: debugger\ioctl.htm
old-project: debugger
ms.assetid: fe35d032-fa34-44a7-9e61-dcb1ca2a2e85
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Ioctl, Ioctl callback function [Windows Debugging], PWINDBG_IOCTL_ROUTINE, WdbgExts_Ref_fa1f5367-924d-478c-a3cb-ca08bf8dde2f.xml, debugger.ioctl, wdbgexts/Ioctl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
api_location:
-	wdbgexts.h
api_name:
-	Ioctl
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---

# PWINDBG_IOCTL_ROUTINE callback


## -description


The <b>PWINDBG_IOCTL_ROUTINE</b> (<b>Ioctl</b>) function performs a variety of different operations. Much of its functionality mirrors the functionality of other functions in wdbgexts.h.


## -prototype


````
ULONG Ioctl(
   USHORT IoctlType,
   PVOID  lpvData,
   ULONG  cbSizeOfContext
);
````


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

<a href="..\wdbgexts\nf-wdbgexts-getkdcontext.md">GetKdContext</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_CONTROL_SPACE

</td>
<td>

<a href="..\wdbgexts\ns-wdbgexts-_readcontrolspace.md">ReadControlSpace</a>


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

<a href="..\wdbgexts\nf-wdbgexts-readiospace.md">ReadIoSpace</a>


<b>ReadIoSpace64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_IO_SPACE

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-writeiospace.md">WriteIoSpace</a>


<b>WriteIoSpace64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_PHYSICAL

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-readphysical.md">ReadPhysical</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_PHYSICAL

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-writephysical.md">WritePhysical</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_IO_SPACE_EX

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-readiospaceex.md">ReadIoSpaceEx</a>


<b>ReadIoSpaceEx64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_IO_SPACE_EX

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-writeiospaceex.md">WriteIoSpaceEx</a>


<b>WriteIoSpaceEx64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_SET_THREAD

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-setthreadforoperation.md">SetThreadForOperation</a>


<b>SetThreadForOperation64 </b>

</td>
<td></td>
</tr>
<tr>
<td>
IG_READ_MSR

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-readmsr.md">ReadMsr</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_WRITE_MSR

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-writemsr.md">WriteMsr</a>


</td>
<td></td>
</tr>
<tr>
<td>
IG_GET_DEBUGGER_DATA

</td>
<td>

<a href="..\wdbgexts\nf-wdbgexts-getdebuggerdata.md">GetDebuggerData</a>


</td>
<td></td>
</tr>
<tr>
<td>

                IG_GET_KERNEL_VERSION

</td>
<td></td>
<td>

<a href="..\wdbgexts\ns-wdbgexts-_dbgkd_get_version64.md">DBGKD_GET_VERSION64</a>


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

<a href="..\wdbgexts\nf-wdbgexts-getsetsympath.md">GetSetSympath</a>


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

<a href="https://msdn.microsoft.com/aca1fe96-20c7-4a51-a331-583b107f62e0">GETSETBUSDATA</a>


</td>
</tr>
<tr>
<td>

                IG_SET_BUS_DATA

</td>
<td></td>
<td>

<a href="https://msdn.microsoft.com/aca1fe96-20c7-4a51-a331-583b107f62e0">GETSETBUSDATA</a>


</td>
</tr>
<tr>
<td>

<a href="..\wdbgexts\ns-wdbgexts-_sym_dump_param.md">IG_DUMP_SYMBOL_INFO</a>


</td>
<td></td>
<td>

<a href="..\wdbgexts\ns-wdbgexts-_sym_dump_param.md">SYM_DUMP_PARAM</a>


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

<a href="..\wdbgexts\ns-wdbgexts-_pointer_search_physical.md">POINTER_SEARCH_PHYSICAL</a>


</td>
</tr>
<tr>
<td>

                IG_GET_THREAD_OS_INFO

</td>
<td>


</td>
<td>

<a href="..\wdbgexts\ns-wdbgexts-_wdbgexts_thread_os_info.md">WDBGEXTS_THREAD_OS_INFO</a>


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



