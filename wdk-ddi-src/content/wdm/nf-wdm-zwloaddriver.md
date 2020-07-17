---
UID: NF:wdm.ZwLoadDriver
title: ZwLoadDriver function (wdm.h)
description: The ZwLoadDriver routine loads a driver into the system.
old-location: kernel\zwloaddriver.htm
tech.root: kernel
ms.assetid: ab5afdc8-d4d3-4be0-a613-d92f1b847b27
ms.date: 04/30/2018
keywords: ["ZwLoadDriver function"]
ms.keywords: NtLoadDriver, ZwLoadDriver, ZwLoadDriver routine [Kernel-Mode Driver Architecture], k111_b421f181-1a7d-4122-a73c-604f6b98686d.xml, kernel.zwloaddriver, wdm/NtLoadDriver, wdm/ZwLoadDriver
f1_keywords:
 - "wdm/ZwLoadDriver"
 - "ZwLoadDriver"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwLoadDriver
- NtLoadDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwLoadDriver function


## -description


The <b>ZwLoadDriver</b> routine loads a driver into the system. 


## -parameters




### -param DriverServiceName [in]

Pointer to a counted Unicode string that specifies a path to the driver's registry key, \Registry\Machine\System\CurrentControlSet\Services\\<_DriverName_>, where <_DriverName_> is the name of the driver. 


## -returns



<b>ZwLoadDriver</b> returns STATUS_SUCCESS or an appropriate error NTSTATUS value. 




## -remarks



<b>ZwLoadDriver</b> dynamically loads a device or file system driver into the currently running system. 

<div class="alert"><b>Note</b>    If the system is running in safe mode, and the driver fails to load because it is not on the safe mode list, <b>ZwLoadDriver</b> returns STATUS_SUCCESS. </div>
<div> </div>
A minifilter should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltloadfilter">FltLoadFilter</a> instead of <b>ZwLoadDriver</b> to load a supporting minifilter.

<div class="alert"><b>Note</b>  If the call to the <b>ZwLoadDriver</b> function occurs in user mode, you should use the name "<b>NtLoadDriver</b>" instead of "<b>ZwLoadDriver</b>". </div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltloadfilter">FltLoadFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwunloaddriver">ZwUnloadDriver</a>
 

 

