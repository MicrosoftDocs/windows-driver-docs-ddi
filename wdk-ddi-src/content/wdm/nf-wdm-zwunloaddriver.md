---
UID: NF:wdm.ZwUnloadDriver
title: ZwUnloadDriver function
author: windows-driver-content
description: The ZwUnloadDriver routine unloads a driver from the system.
old-location: kernel\zwunloaddriver.htm
old-project: kernel
ms.assetid: 4fbb4d4b-b98a-4d10-b9b2-7ad8fc4ada6e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ZwUnloadDriver
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
req.alt-api: ZwUnloadDriver,NtUnloadDriver
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwUnloadDriver function



## -description
The <b>ZwUnloadDriver</b> routine unloads a driver from the system. <i>Use this routine with extreme caution. (See the following </i><b>Remarks</b><i> section.)</i>



## -syntax

````
NTSTATUS ZwUnloadDriver(
  _In_ PUNICODE_STRING DriverServiceName
);
````


## -parameters

### -param DriverServiceName [in]

Pointer to a counted Unicode string that specifies a path to the driver's registry key, <b>\Registry\Machine\System\CurrentControlSet\Services\</b><i>DriverName</i>, where <i>DriverName</i> is the name of the driver. 


## -returns
<b>ZwUnloadDriver</b> returns STATUS_SUCCESS or an error NTSTATUS value such as STATUS_INVALID_DEVICE_REQUEST. 


## -remarks
<b>ZwUnloadDriver</b> dynamically unloads a device or file system driver from the currently running system. 

<i>Note that a file system filter driver cannot safely be unloaded from a running system. Thus a filter should only use </i><b><i>ZwUnloadDriver</i></b><i> for debugging purposes. It should not call this routine in a retail version of the filter. </i>

If <i>DriverName</i> is the name of a PnP device driver, <b>ZwUnloadDriver</b> returns STATUS_INVALID_DEVICE_REQUEST and does not unload the driver. 

A minifilter should use <a href="..\fltkernel\nf-fltkernel-fltunloadfilter.md">FltUnloadFilter</a> instead of <b>ZwUnloadDriver</b> to unload a supporting minifilter. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltunloadfilter.md">FltUnloadFilter</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwloaddriver.md">ZwLoadDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwUnloadDriver routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

