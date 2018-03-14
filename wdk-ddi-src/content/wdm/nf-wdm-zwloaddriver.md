---
UID: NF:wdm.ZwLoadDriver
title: ZwLoadDriver function
author: windows-driver-content
description: The ZwLoadDriver routine loads a driver into the system.
old-location: kernel\zwloaddriver.htm
old-project: kernel
ms.assetid: ab5afdc8-d4d3-4be0-a613-d92f1b847b27
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: NtLoadDriver, ZwLoadDriver, ZwLoadDriver routine [Kernel-Mode Driver Architecture], k111_b421f181-1a7d-4122-a73c-604f6b98686d.xml, kernel.zwloaddriver, wdm/NtLoadDriver, wdm/ZwLoadDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwLoadDriver
-	NtLoadDriver
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwLoadDriver function


## -description


The <b>ZwLoadDriver</b> routine loads a driver into the system. 


## -syntax


````
NTSTATUS ZwLoadDriver(
  _In_ PUNICODE_STRING DriverServiceName
);
````


## -parameters




### -param DriverServiceName [in]

Pointer to a counted Unicode string that specifies a path to the driver's registry key, <b>\Registry\Machine\System\CurrentControlSet\Services\<i>DriverName</i></b>, where <i>DriverName</i> is the name of the driver. 


## -returns



<b>ZwLoadDriver</b> returns STATUS_SUCCESS or an appropriate error NTSTATUS value. 




## -remarks



<b>ZwLoadDriver</b> dynamically loads a device or file system driver into the currently running system. 

<div class="alert"><b>Note</b>    If the system is running in safe mode, and the driver fails to load because it is not on the safe mode list, <b>ZwLoadDriver</b> returns STATUS_SUCCESS. </div>
<div> </div>
A minifilter should use <a href="..\fltkernel\nf-fltkernel-fltloadfilter.md">FltLoadFilter</a> instead of <b>ZwLoadDriver</b> to load a supporting minifilter.

<div class="alert"><b>Note</b>  If the call to the <b>ZwLoadDriver</b> function occurs in user mode, you should use the name "<b>NtLoadDriver</b>" instead of "<b>ZwLoadDriver</b>". </div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\wdm\nf-wdm-zwunloaddriver.md">ZwUnloadDriver</a>



<a href="..\fltkernel\nf-fltkernel-fltloadfilter.md">FltLoadFilter</a>



 

 


