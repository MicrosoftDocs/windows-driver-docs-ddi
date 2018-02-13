---
UID: NF:wdm.RtlDeleteRegistryValue
title: RtlDeleteRegistryValue function
author: windows-driver-content
description: The RtlDeleteRegistryValue routine removes the specified entry name and the associated values from the registry along the given relative path.
old-location: kernel\rtldeleteregistryvalue.htm
old-project: kernel
ms.assetid: 4bbedc96-a7e2-40bd-98f3-c1136f70564d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/RtlDeleteRegistryValue, RtlDeleteRegistryValue, RtlDeleteRegistryValue routine [Kernel-Mode Driver Architecture], kernel.rtldeleteregistryvalue, k109_ad2e98c7-7787-49b2-b2af-1782d7f64e0d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlRtlPassive, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlDeleteRegistryValue
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlDeleteRegistryValue function


## -description


The <b>RtlDeleteRegistryValue</b> routine removes the specified entry name and the associated values from the registry along the given relative path.


## -syntax


````
NTSTATUS RtlDeleteRegistryValue(
  _In_ ULONG  RelativeTo,
  _In_ PCWSTR Path,
  _In_ PCWSTR ValueName
);
````


## -parameters




### -param RelativeTo [in]

Specifies whether <i>Path</i> is an absolute registry path or is relative to a predefined key path as one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
RTL_REGISTRY_ABSOLUTE

</td>
<td>
Path is an absolute registry path.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_SERVICES

</td>
<td>
Path is relative to <b>\Registry\Machine\System\CurrentControlSet\Services</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_CONTROL

</td>
<td>
Path is relative to <b>\Registry\Machine\System\CurrentControlSet\Control</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_WINDOWS_NT

</td>
<td>
Path is relative to <b>\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_DEVICEMAP

</td>
<td>
Path is relative to <b>\Registry\Machine\Hardware\DeviceMap</b>.

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_USER

</td>
<td>
Path is relative to <b>\Registry\User\CurrentUser</b>. (For a system process, this is <b>\Users\.Default</b>.)

</td>
</tr>
<tr>
<td>
RTL_REGISTRY_HANDLE

</td>
<td>
Specifies that the <i>Path</i> parameter is actually a registry handle to use. This value is optional.

</td>
</tr>
</table>
 


### -param Path [in]

Specifies the registry path according to the <i>RelativeTo</i> value. If RTL_REGISTRY_HANDLE is set, <i>Path</i> is a handle to be used directly.


### -param ValueName [in]

Pointer to the value name to be removed from the registry.


## -returns



<b>RtlDeleteRegistryValue</b> returns STATUS_SUCCESS if the value entry was deleted.

Note that if <i>RelativeTo</i> is set to RTL_REGISTRY_HANDLE, the following occurs:

<ul>
<li>
On Windows 98/Me and Windows NT 4.0, the routine closes the specified handle before returning.

</li>
<li>
On Windows 2000 and later versions of Windows, the routine leaves the handle open.

</li>
</ul>



## -see-also

<a href="..\wdm\nf-wdm-rtlcheckregistrykey.md">RtlCheckRegistryKey</a>



<a href="..\wdm\nf-wdm-rtlwriteregistryvalue.md">RtlWriteRegistryValue</a>



<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>



<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>



<a href="..\wdm\nf-wdm-rtlqueryregistryvalues.md">RtlQueryRegistryValues</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlDeleteRegistryValue routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

