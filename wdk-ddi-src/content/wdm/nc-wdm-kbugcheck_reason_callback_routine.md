---
UID: NC:wdm.KBUGCHECK_REASON_CALLBACK_ROUTINE
title: KBUGCHECK_REASON_CALLBACK_ROUTINE
author: windows-driver-content
description: Driver-implemented callback functions that the system executes when it issues a bug check.
old-location: kernel\bugcheckaddpagescallback.htm
old-project: kernel
ms.assetid: a3d33a3a-efe7-4346-82bc-555c57ae7b74
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.bugcheckaddpagescallback, BugCheckAddPagesCallback, BugCheckDumpIoCallback, BugCheckSecondaryDumpDataCallback, MyBugCheckCallback callback function [Kernel-Mode Driver Architecture], MyBugCheckCallback, KBUGCHECK_REASON_CALLBACK_ROUTINE, KBUGCHECK_REASON_CALLBACK_ROUTINE, wdm/MyBugCheckCallback, DrvrRtns_337f5b60-9ed5-4a1b-a215-1d3b1e3abb1e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows Server 2008.
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
req.irql: Called at HIGH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	MyBugCheckCallback
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# KBUGCHECK_REASON_CALLBACK_ROUTINE callback


## -description


Driver-implemented callback functions that the system executes when it issues a bug check.

The <i>BugCheckAddPagesCallback</i> routine adds one or more pages of data to the crash dump file when the operating system issues a bug check.

The <i>BugCheckDumpIoCallback</i> routine is executed each time the system writes data to a crash dump file.

The <i>BugCheckSecondaryDumpDataCallback</i> routine provides data to the system to append to the crash dump file when the system issues a bug check.


## -prototype


````
KBUGCHECK_REASON_CALLBACK_ROUTINE MyBugCheckCallback;

VOID MyBugCheckCallback(
  _In_    KBUGCHECK_CALLBACK_REASON                Reason,
  _In_    struct _KBUGCHECK_REASON_CALLBACK_RECORD *Record,
  _Inout_ PVOID                                    ReasonSpecificData,
  _In_    ULONG                                    ReasonSpecificDataLength
)
{ ... }
````


## -parameters




### -param Reason [in]

Specifies the reason for the call to the callback routine. This value can be one of the following as defined in  <a href="..\wdm\ne-wdm-_kbugcheck_callback_reason.md">KBUGCHECK_CALLBACK_REASON</a>

<ul>
<li><b>KbCallbackAddPages</b>: The purpose of the callback function is to enable the driver to add pages of data to the crash dump file. </li>
<li><b>KbCallbackDumpIo</b>: This callback function is executed each time the system writes data to a crash dump file.</li>
<li><b>KbCallbackSecondaryDumpData</b>: This callback function provides data to the system to append to the crash dump file when the system issues a bug check.</li>
</ul>

### -param Record [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a> structure that the driver supplied when it registered this callback. For more information, see the description of the <i>CallbackRecord</i> parameter in <a href="..\wdm\nf-wdm-keregisterbugcheckcallback.md">KeRegisterBugCheckCallback</a>.


### -param ReasonSpecificData [in, out]

A pointer to a <a href="..\wdm\ns-wdm-_kbugcheck_add_pages.md">KBUGCHECK_ADD_PAGES</a> structure. This pointer is cast to type PVOID. Certain members of this structure are filled in by the operating system before it calls the callback routine, and other members must be filled in by the callback routine. For more information, see the following Remarks section.


### -param ReasonSpecificDataLength [in]

Specifies the size, in bytes, of the buffer that the <i>ReasonSpecificData</i> parameter points to. 
<ul>
<li><b>KbCallbackAddPages</b>: <b>sizeof</b>(<b>KBUGCHECK_ADD_PAGES</b>). </li>
<li><b>KbCallbackDumpIo</b>: <b>sizeof</b>(<b>KBUGCHECK_DUMP_IO</b>).</li>
<li><b>KbCallbackSecondaryDumpData</b>: <b>sizeof</b>(<b>KBUGCHECK_SECONDARY_DUMP_DATA</b>). </li>
</ul>

## -returns


None.



## -remarks


<b>About implementing <i>BugCheckAddPagesCallback</i>:  </b>A kernel-mode driver can implement a <i>BugCheckAddPagesCallback</i> callback routine to add one or more pages of data to a crash dump file when a bug check occurs. To register this routine with the operating system, the driver calls the <a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a> routine. Before the driver unloads, it must call the <a href="..\wdm\nf-wdm-kederegisterbugcheckreasoncallback.md">KeDeregisterBugCheckReasonCallback</a> routine to remove the registration.

Starting with Windows 8, a registered <i>BugCheckAddPagesCallback</i> routine is called during a <a href="http://go.microsoft.com/fwlink/p/?linkid=178118">kernel memory dump</a> or a <a href="http://go.microsoft.com/fwlink/p/?linkid=178119">complete memory dump</a>. In earlier versions of Windows, a registered <i>BugCheckAddPagesCallback</i> routine is called during a kernel memory dump, but not during a complete memory dump. By default, a kernel memory dump includes only the physical pages that are being used by the Windows kernel at the time that the bug check occurs, whereas a complete memory dump includes all of the physical memory that is used by Windows. A complete memory dump does not, by default, include physical memory that is used by the platform firmware.

Your <i>BugCheckAddPagesCallback</i> routine can supply driver-specific data to add to the dump file. For example, for a kernel memory dump, this additional data can include physical pages that are not mapped to the system address range in virtual memory but that contain information that can help you to debug your driver. The <i>BugCheckAddPagesCallback</i> routine might add to the dump file any driver-owned physical pages that are unmapped or that are mapped to user-mode addresses in virtual memory.

When a bug check occurs, the operating system calls all the registered <i>BugCheckAddPagesCallback</i> routines to poll drivers for data to add to the crash dump file. Each call adds one or more pages of contiguous data to the crash dump file. A <i>BugCheckAddPagesCallback</i> routine can supply either a virtual address or a physical address for the starting page. If more than one page is supplied during a call, the pages are contiguous in either virtual or physical memory, depending on whether the starting address is virtual or physical. To supply noncontiguous pages, the <i>BugCheckAddPagesCallback</i> routine can set a flag in the <b>KBUGCHECK_ADD_PAGES</b> structure to indicate that it has additional data and has to be called again. For more information, see <a href="..\wdm\ns-wdm-_kbugcheck_add_pages.md">KBUGCHECK_ADD_PAGES</a>.

Unlike a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a> routine, which appends data to the secondary crash dump region, a <i>BugCheckAddPagesCallback</i> routine adds pages of data to the primary crash dump region. During debugging, primary crash dump data is easier to access than secondary crash dump data.

Before the operating system calls a <i>BugCheckAddPagesCallback</i> routine, it fills in the <b>BugCheckCode</b> member of the <b>KBUGCHECK_ADD_PAGES</b> structure that <i>ReasonSpecificData</i> points to. During the call, the <i>BugCheckAddPagesCallback</i> routine must set the values of the <b>Flags</b>, <b>Address</b>, and <b>Count</b> members of this structure. If the <i>BugCheckAddPagesCallback</i> routine is called more than one time, the operating system preserves the value that the callback routine wrote to the <b>Context</b> member in the previous call. Before the first call, the operating system initializes <b>Context</b> to <b>NULL</b>.

A <i>BugCheckAddPagesCallback</i> routine is very restricted in the actions it can take. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566401">Writing a Bug Check Callback Routine</a>.



<b>About implementing <i>BugCheckDumpIoCallback</i>:  </b>The driver's <i>BugCheckDumpIoCallback</i> routine is called each time data is written to the crash dump file. The system passes, in the <i>ReasonSpecificData</i> parameter, a description of the data being written. The <b>Buffer</b> member points to the current data, and the <b>BufferLength</b> member specifies its length. The <b>Type</b> member indicates the type of data currently being written, such as dump file header information, memory state, or data provided by a driver. For a description of the possible types of information, see <a href="..\wdm\ne-wdm-_kbugcheck_dump_io_type.md">KBUGCHECK_DUMP_IO_TYPE</a>.

The system can write the crash dump file either sequentially, or out of order. If the system is writing the crash dump file sequentially, then the <b>Offset</b> member of <i>ReasonSpecificData</i> is -1; otherwise, <b>Offset</b> is set to the current offset, in bytes, in the crash dump file.

When the system writes the file sequentially, it calls each <i>BugCheckDumpIoCallback</i> routine one or more times when writing the header information (<b>Type</b> = <b>KbDumpIoHeader</b>), one or more times when writing the main body of the crash dump file (<b>Type</b> = <b>KbDumpIoBody</b>), and one or more times when writing the secondary dump data (<b>Type</b> = <b>KbDumpIoSecondaryDumpData</b>). Once the system has completed writing the crash dump file, it calls the callback with <b>Buffer</b> = <b>NULL</b>, <b>BufferLength</b> = 0, and <b>Type</b> = <b>KbDumpIoComplete</b>.

The main purpose of a <i>BugCheckDumpIoCallback</i> routine is to allow system crash dump data to be written to devices other than the disk. For example, a device that monitors system state can use the callback to report that the system has issued a bug check, and to provide a crash dump for analysis.

Use <a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a> to register a <i>BugCheckDumpIoCallback</i> routine. A driver can subsequently remove the callback by using the <a href="..\wdm\nf-wdm-kederegisterbugcheckreasoncallback.md">KeDeregisterBugCheckReasonCallback</a> routine. If the driver can be unloaded, it must remove any registered callbacks in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine.

A <i>BugCheckDumpIoCallback</i> routine is strongly restricted in the actions it can take. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566401">Writing a Bug Check Callback Routine</a>.



<b>About implementing <i>BugCheckSecondaryDumpDataCallback</i>:  </b>The system uses <i>BugCheckSecondaryDumpDataCallback</i> routines to poll drivers for crash dump data.

The system sets the <b>InBuffer</b>, <b>InBufferLength</b>, <b>OutBuffer</b>, and <b>MaximumAllowed</b> members of the <a href="..\wdm\ns-wdm-_kbugcheck_secondary_dump_data.md">KBUGCHECK_SECONDARY_DUMP_DATA</a> structure that <i>ReasonSpecificData</i> points to. The <b>MaximumAllowed</b> member specifies the maximum amount of dump data the routine can provide.

The value of the <b>OutBuffer</b> member determines whether the system is requesting the size of the driver's dump data, or the data itself, as follows:

<ul>
<li>
If the <b>OutBuffer</b> member of KBUGCHECK_SECONDARY_DUMP_DATA is <b>NULL</b>, the system is only requesting size information. The <i>BugCheckSecondaryDumpDataCallback</i> routine fills in the <b>OutBuffer</b> and <b>OutBufferLength</b> members. 

</li>
<li>
If the <b>OutBuffer</b> member of KBUGCHECK_SECONDARY_DUMP_DATA equals the <b>InBuffer</b> member, the system is requesting the driver's secondary dump data. The <i>BugCheckSecondaryDumpDataCallback</i> routine fills in the <b>OutBuffer</b> and <b>OutBufferLength</b> members, and writes the data to the buffer specified by <b>OutBuffer</b>.

</li>
</ul>
The <b>InBuffer</b> member of KBUGCHECK_SECONDARY_DUMP_DATA points  to a small buffer for the routine's use. The <b>InBufferLength</b> member specifies the size of the buffer. If the amount of data to be written is less than <b>InBufferLength</b>, the callback routine can use this buffer to supply the crash dump data to the system. The callback routine then sets <b>OutBuffer</b> to <b>InBuffer</b> and <b>OutBufferLength</b> to the actual amount of data written to the buffer.

A driver that must write an amount of data that is larger than <b>InBufferLength</b> can use its own buffer to provide the data. This buffer must have been allocated before the callback routine is executed, and must reside in resident memory (such as nonpaged pool). The callback routine then sets <b>OutBuffer</b> to point to the driver's buffer, and <b>OutBufferLength</b> to the amount of data in the buffer to be written to the crash dump file.

In Windows XP and Windows Server 2003, if <b>OutBuffer</b> is set to point to a driver-allocated buffer, the buffer must begin on a page-aligned boundary in memory. Otherwise, no data is written to the secondary data area of the crash dump file. In Windows Vista and later versions of Windows, there is no such alignment requirement.

Each block of data to be written to the crash dump file is tagged with the value of the <b>Guid</b> member of <a href="..\wdm\ns-wdm-_kbugcheck_secondary_dump_data.md">KBUGCHECK_SECONDARY_DUMP_DATA</a>. The GUID used must be unique to the driver. To display the secondary dump data corresponding to this GUID, you can use the <b>.enumtag</b> command or the <b>IDebugDataSpaces3::ReadTagged</b> method in a debugger extension. For information about debuggers and debugger extensions, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.

A driver can write multiple blocks with the same GUID to the crash dump file, but this is very poor practice, because only the first block will be accessible to the debugger. Drivers that register multiple <i>BugCheckSecondaryDumpDataCallback</i> routines should allocate a unique GUID for each callback.

Use <a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a> to register a <i>BugCheckSecondaryDumpDataCallback</i> routine. A driver can subsequently remove the callback routine by using the <a href="..\wdm\nf-wdm-kederegisterbugcheckreasoncallback.md">KeDeregisterBugCheckReasonCallback</a> routine. If the driver can be unloaded, then it must remove any registered callback routines in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine.

A <i>BugCheckSecondaryDumpDataCallback</i> is very restricted in the actions it can take. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566401">Writing a Bug Check Callback Routine</a>. 





## -see-also

<a href="..\wdm\ne-wdm-_kbugcheck_callback_reason.md">KBUGCHECK_CALLBACK_REASON</a>

<a href="..\wdm\nf-wdm-kederegisterbugcheckreasoncallback.md">KeDeregisterBugCheckReasonCallback</a>

<a href="..\wdm\ns-wdm-_kbugcheck_add_pages.md">KBUGCHECK_ADD_PAGES</a>

<a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KBUGCHECK_REASON_CALLBACK_ROUTINE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

