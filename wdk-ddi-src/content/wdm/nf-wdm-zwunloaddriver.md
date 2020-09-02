---
UID: NF:wdm.ZwUnloadDriver
title: ZwUnloadDriver function (wdm.h)
description: The ZwUnloadDriver routine unloads a driver from the system.
old-location: kernel\zwunloaddriver.htm
tech.root: kernel
ms.assetid: 4fbb4d4b-b98a-4d10-b9b2-7ad8fc4ada6e
ms.date: 04/30/2018
keywords: ["ZwUnloadDriver function"]
ms.keywords: NtUnloadDriver, ZwUnloadDriver, ZwUnloadDriver routine [Kernel-Mode Driver Architecture], k111_72ac4415-d46c-4ea2-9d6c-d66903082808.xml, kernel.zwunloaddriver, wdm/NtUnloadDriver, wdm/ZwUnloadDriver
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwUnloadDriver
 - wdm/ZwUnloadDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwUnloadDriver
 - NtUnloadDriver
---

# ZwUnloadDriver function


## -description

The <b>ZwUnloadDriver</b> routine unloads a driver from the system. <i>Use this routine with extreme caution. (See the following </i><b>Remarks</b><i> section.)</i>

## -parameters

### -param DriverServiceName 

[in]
Pointer to a counted Unicode string that specifies a path to the driver's registry key, `\Registry\Machine\System\CurrentControlSet\Services\<DriverName>`, where <i>DriverName</i> is the name of the driver.

## -returns

<b>ZwUnloadDriver</b> returns STATUS_SUCCESS or an error NTSTATUS value such as STATUS_INVALID_DEVICE_REQUEST.

## -remarks

<b>ZwUnloadDriver</b> dynamically unloads a device or file system driver from the currently running system. 

<i>Note that a file system filter driver cannot safely be unloaded from a running system. Thus a filter should only use </i><b><i>ZwUnloadDriver</i></b><i> for debugging purposes. It should not call this routine in a retail version of the filter. </i>

If <i>DriverName</i> is the name of a PnP device driver, <b>ZwUnloadDriver</b> returns STATUS_INVALID_DEVICE_REQUEST and does not unload the driver. 

A minifilter should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltunloadfilter">FltUnloadFilter</a> instead of <b>ZwUnloadDriver</b> to unload a supporting minifilter. 

<div class="alert"><b>Note</b>  If the call to the <b>ZwUnloadDriver</b> function occurs in user mode, you should use the name "<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwunloaddriver">NtUnloadDriver</a>" instead of "<b>ZwUnloadDriver</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltunloadfilter">FltUnloadFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwloaddriver">ZwLoadDriver</a>

