---
UID: NA:wdbgexts
ms.assetid: 47d4ebbf-84ee-3898-8135-fa80fd566021
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdbgexts.h header



This header is used by Debugger. For more information, see
- [Debugger](../_debugger/index.md)

Wdbgexts.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [GetCurrentProcessAddr function](nf-wdbgexts-getcurrentprocessaddr.md) | The GetCurrentProcessAddr function returns the location of the system data that describes the current process. |
| [GetCurrentProcessHandle function](nf-wdbgexts-getcurrentprocesshandle.md) | The GetCurrentProcessHandle function returns the system handle for the current process. |
| [GetCurrentThreadAddr function](nf-wdbgexts-getcurrentthreadaddr.md) | The GetCurrentThreadAddr function returns the location of the system data that describes the current thread. |
| [GetDebuggerCacheSize function](nf-wdbgexts-getdebuggercachesize.md) | The GetDebuggerCacheSize function returns the size of the cache that is used by the debugger to hold data that was obtained from the target. |
| [GetExpressionEx function](nf-wdbgexts-getexpressionex.md) | The GetExpressionEx function evaluates an expression. The expression is evaluated using the MASM evaluator, and can contain aliases. |
| [GetFieldData function](nf-wdbgexts-getfielddata.md) | The GetFieldData function returns the value of a member in a structure. |
| [GetFieldOffset function](nf-wdbgexts-getfieldoffset.md) | The GetFieldOffset function returns the offset of a member from the beginning of a structure. |
| [GetInputLine function](nf-wdbgexts-getinputline.md) | The GetInputLine function requests an input string from the debugger. |
| [GetPebAddress function](nf-wdbgexts-getpebaddress.md) | The GetPebAddress function returns the address of the process environment block (PEB) for a system process. |
| [GetSetSympath function](nf-wdbgexts-getsetsympath.md) | The GetSetSympath function can be used to either get or set the symbol search path. |
| [GetShortField function](nf-wdbgexts-getshortfield.md) | The GetShortField function reads the value of a member in a structure if its size is less than or equal to 8 bytes, or initializes a structure so it can be read later. |
| [GetTebAddress function](nf-wdbgexts-gettebaddress.md) | The GetTebAddress function returns the address of the thread environment block (TEB) for the current operating system thread. |
| [GetTypeSize function](nf-wdbgexts-gettypesize.md) | The GetTypeSize function returns the size in the target's memory of an instance of the specified type. |
| [IsPtr64 function](nf-wdbgexts-isptr64.md) | The IsPtr64 function determines if the target uses 64-bit pointers. |
| [ListType function](nf-wdbgexts-listtype.md) | The ListType function calls a specified callback function for every element in a linked list. |
| [ReadControlSpace function](nf-wdbgexts-readcontrolspace.md) | The ReadControlSpace function reads the processor-specific control space into the array pointed to by buf. |
| [ReadControlSpace64 function](nf-wdbgexts-readcontrolspace64.md) | The ReadControlSpace64 function reads the processor-specific control space into the array pointed to by buf. |
| [ReadIoSpace function](nf-wdbgexts-readiospace.md) | The ReadIoSpace function reads from the system I/O locations. |
| [ReadIoSpace64 function](nf-wdbgexts-readiospace64.md) | The ReadIoSpace64 function reads from the system I/O locations. |
| [ReadIoSpaceEx function](nf-wdbgexts-readiospaceex.md) | The ReadIoSpaceEx function is an extended version of ReadIoSpace. |
| [ReadIoSpaceEx64 function](nf-wdbgexts-readiospaceex64.md) | The ReadIoSpaceEx64 function is an extended version of ReadIoSpace64. |
| [ReadListEntry function](nf-wdbgexts-readlistentry.md) | The ReadListEntry function reads a doubly-linked list entry from the target's memory. |
| [ReadMsr function](nf-wdbgexts-readmsr.md) | The ReadMsr function reads the contents of a Model-Specific Register (MSR). |
| [ReadPhysical function](nf-wdbgexts-readphysical.md) | The ReadPhysical function reads from physical memory. |
| [ReadPhysicalWithFlags function](nf-wdbgexts-readphysicalwithflags.md) | The ReadPhysicalWithFlags function reads from physical memory. |
| [ReadPointer function](nf-wdbgexts-readpointer.md) | The ReadPointer function reads a pointer from the target. |
| [ReadPtr function](nf-wdbgexts-readptr.md) | The ReadPtr function reads a pointer from the target. ReadPointer should be used instead of this function as the return value of ReadPointer is more consistent with the rest of the WdbgExts API. |
| [ReloadSymbols function](nf-wdbgexts-reloadsymbols.md) | The ReloadSymbols function deletes symbol information from the debugger so that it can be reloaded as needed. This function behaves the same way as the debugger command .reload. |
| [SearchMemory function](nf-wdbgexts-searchmemory.md) | The SearchMemory function searches the target's virtual memory for a specified pattern of bytes. |
| [SetThreadForOperation function](nf-wdbgexts-setthreadforoperation.md) | The SetThreadForOperation function sets the thread to use for the next StackTrace call. |
| [SetThreadForOperation64 function](nf-wdbgexts-setthreadforoperation64.md) | The SetThreadForOperation64 function sets the thread to use for the next StackTrace call. |
| [TranslateVirtualToPhysical function](nf-wdbgexts-translatevirtualtophysical.md) | The TranslateVirtualToPhysical function translates a virtual memory address into a physical memory address. |
| [WriteControlSpace function](nf-wdbgexts-writecontrolspace.md) | The WriteControlSpace function writes to the processor-specific control space of the current target. |
| [WriteIoSpace function](nf-wdbgexts-writeiospace.md) | The WriteIoSpace function writes to the system I/O locations. |
| [WriteIoSpace64 function](nf-wdbgexts-writeiospace64.md) | The WriteIoSpace64 function writes to the system I/O locations. |
| [WriteIoSpaceEx function](nf-wdbgexts-writeiospaceex.md) | The WriteIoSpaceEx function is an extended version of WriteIoSpace. |
| [WriteIoSpaceEx64 function](nf-wdbgexts-writeiospaceex64.md) | The WriteIoSpaceEx64 function is an extended version of WriteIoSpace64. |
| [WriteMsr function](nf-wdbgexts-writemsr.md) | The WriteMsr function writes to a Model-Specific Register (MSR). |
| [WritePhysical function](nf-wdbgexts-writephysical.md) | The WritePhysical function writes to physical memory. |
| [WritePhysicalWithFlags function](nf-wdbgexts-writephysicalwithflags.md) | The WritePhysicalWithFlags function writes to physical memory. |
| [WritePointer function](nf-wdbgexts-writepointer.md) | The WritePointer function writes a pointer to the target. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PSYM_DUMP_FIELD_CALLBACK callback](nc-wdbgexts-psym_dump_field_callback.md) | The PSYM_DUMP_FIELD_CALLBACK callback function is called by the debugger engine during the IG_DUMP_SYMBOL_INFO Ioctl operation with information about a member in the specified symbol. |
| [PWINDBG_CHECK_CONTROL_C callback](nc-wdbgexts-pwindbg_check_control_c.md) | The PWINDBG_CHECK_CONTROL_C (CheckControlC) function checks to see if the user pressed CTRL+C. Use PWINDBG_CHECK_CONTROL_C in all loops to allow the user to press CTRL+C to end long processes. |
| [PWINDBG_CHECK_VERSION callback](nc-wdbgexts-pwindbg_check_version.md) | The PWINDBG_CHECK_VERSION (CheckVersion) callback function verifies that the extension module version matches the debugger version, and outputs an warning message if there is a mismatch. |
| [PWINDBG_DISASM callback](nc-wdbgexts-pwindbg_disasm.md) | The PWINDBG_DISASM (Disasm) function disassembles the instruction pointed to by lpOffset and places the printable string into lpBuffer. |
| [PWINDBG_EXTENSION_API_VERSION callback](nc-wdbgexts-pwindbg_extension_api_version.md) | The PWINDBG_EXTENSION_API_VERSION (ExtensionApiVersion) callback function returns version information about the extension DLL. |
| [PWINDBG_EXTENSION_DLL_INIT callback](nc-wdbgexts-pwindbg_extension_dll_init.md) | The PWINDBG_EXTENSION_DLL_INIT ( WinDbgExtensionDllInit) callback function is used to load and initialize the extension module. |
| [PWINDBG_GET_EXPRESSION callback](nc-wdbgexts-pwindbg_get_expression.md) | The PWINDBG_GET_EXPRESSION (GetExpression) function returns the value of expression. The expression is evaluated using the current expression evaluator, and can contain aliases. |
| [PWINDBG_GET_SYMBOL callback](nc-wdbgexts-pwindbg_get_symbol.md) | The PWINDBG_GET_SYMBOL (GetSymbol) function locates the symbol nearest to address. |
| [PWINDBG_GET_THREAD_CONTEXT_ROUTINE callback](nc-wdbgexts-pwindbg_get_thread_context_routine.md) | The PWINDBG_GET_THREAD_CONTEXT_ROUTINE (GetContext) function implements the functionality that is similar to the Microsoft Win32 GetThreadContext routine. It returns the context of the process being debugged. |
| [PWINDBG_IOCTL_ROUTINE callback](nc-wdbgexts-pwindbg_ioctl_routine.md) | The PWINDBG_IOCTL_ROUTINE (Ioctl) function performs a variety of different operations. Much of its functionality mirrors the functionality of other functions in wdbgexts.h. |
| [PWINDBG_OUTPUT_ROUTINE callback](nc-wdbgexts-pwindbg_output_routine.md) | The callback function implements the functionality to print a formatted string to the Debugger Command window. |
| [PWINDBG_READ_PROCESS_MEMORY_ROUTINE callback](nc-wdbgexts-pwindbg_read_process_memory_routine.md) | The PWINDBG_READ_PROCESS_MEMORY_ROUTINE (ReadMemory) function works like the Win32 ReadProcessMemory function. It reads memory from the process being debugged. The entire area to be read must be accessible, or the operation fails. |
| [PWINDBG_SET_THREAD_CONTEXT_ROUTINE callback](nc-wdbgexts-pwindbg_set_thread_context_routine.md) | The PWINDBG_SET_THREAD_CONTEXT_ROUTINE (SetContext) function is similar to the Win32 SetThreadContext routine. It sets the context of the process being debugged. |
| [PWINDBG_STACKTRACE_ROUTINE callback](nc-wdbgexts-pwindbg_stacktrace_routine.md) | The PWINDBG_STACKTRACE_ROUTINE (StackTrace) function retrieves a stack trace for the process being debugged. Returns the number of frames read into the buffer pointed to by StackFrames. |
| [PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE callback](nc-wdbgexts-pwindbg_write_process_memory_routine.md) | The PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE (WriteMemory) function works like the Win32 WriteProcessMemory routine. It writes memory to the process being debugged. The entire area to be written must be accessible, or the operation fails. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_DBGKD_GET_VERSION64 structure](ns-wdbgexts-_dbgkd_get_version64.md) | The IG_GET_KERNEL_VERSION Ioctl operation receives information related to the operating system version of the target. |
| [_DEBUG_TYPED_DATA structure](ns-wdbgexts-_debug_typed_data.md) | The DEBUG_TYPED_DATA structure describes typed data in the memory of the target. |
| [_EXT_TYPED_DATA structure](ns-wdbgexts-_ext_typed_data.md) | The EXT_TYPED_DATA structure is passed to and returned from the DEBUG_REQUEST_EXT_TYPED_DATA_ANSI Request operation. It contains the input and output parameters for the operation as well as specifying which particular suboperation to perform. |
| [_FIELD_INFO structure](ns-wdbgexts-_field_info.md) | The FIELD_INFO structure is used by the IG_DUMP_SYMBOL_INFOIoctl operation to provide information about a member in a structure. |
| [_GETSETBUSDATA structure](ns-wdbgexts-_getsetbusdata.md) | The IG_GET_BUS_DATA Ioctl operation reads data from a system bus and the IG_SET_BUS_DATA Ioctl operation writes data to a system bus. |
| [_POINTER_SEARCH_PHYSICAL structure](ns-wdbgexts-_pointer_search_physical.md) | The IG_POINTER_SEARCH_PHYSICAL Ioctl operation searches the target's physical memory for pointers lying within a specified range. |
| [_SYM_DUMP_PARAM structure](ns-wdbgexts-_sym_dump_param.md) | The IG_DUMP_SYMBOL_INFO Ioctl operation provides information about the type of a symbol. |
| [_WDBGEXTS_THREAD_OS_INFO structure](ns-wdbgexts-_wdbgexts_thread_os_info.md) | The IG_GET_THREAD_OS_INFO Ioctl operation returns information about an operating system thread in the target. When calling Ioctl with IoctlType set to IG_GET_THREAD_OS_INFO, IpvData should contain an instance of the WDBGEXTS_THREAD_OS_INFO structure. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_EXT_TDOP enumeration](ne-wdbgexts-_ext_tdop.md) | The EXT_TDOP enumeration is used in the Operation member of the EXT_TYPED_DATA structure to specify which suboperation the DEBUG_REQUEST_EXT_TYPED_DATA_ANSI Request operation will perform. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [GetDebuggerData macro](nf-wdbgexts-getdebuggerdata.md) | The GetDebuggerData function retrieves information stored in a data block. |
| [GetFieldValue macro](nf-wdbgexts-getfieldvalue.md) | The GetFieldValue macro is a thin wrapper around the GetFieldData function. It is provided as a convenience for reading the value of a member in a structure. |
| [GetKdContext macro](nf-wdbgexts-getkdcontext.md) | The GetKdContext function returns the total number of processors and the number of the current processor in the structure ppi points to. |
