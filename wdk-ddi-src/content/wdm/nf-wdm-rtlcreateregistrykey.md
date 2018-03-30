---
UID: NF:wdm.RtlCreateRegistryKey
title: RtlCreateRegistryKey function
author: windows-driver-content
description: The RtlCreateRegistryKey routine adds a key object in the registry along a given relative path.
old-location: kernel\rtlcreateregistrykey.htm
old-project: kernel
ms.assetid: 2214acc8-b24a-4db4-9ce3-f639291428f2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlCreateRegistryKey, RtlCreateRegistryKey routine [Kernel-Mode Driver Architecture], k109_9a163bcc-501d-453b-b426-a4267d04135c.xml, kernel.rtlcreateregistrykey, wdm/RtlCreateRegistryKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
-	RtlCreateRegistryKey
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlCreateRegistryKey function


## -description


The <b>RtlCreateRegistryKey</b> routine adds a key object in the registry along a given relative path.


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
</table>
 


### -param Path [in]

Specifies the registry path according to the <i>RelativeTo</i> value. 


## -returns



<b>RtlCreateRegistryKey</b> returns STATUS_SUCCESS if the key is created. 




## -remarks



<b>RtlCreateRegistryKey</b> creates only the keys that you specify. It does not create missing keys in the path to the specified key. If any keys in the path are missing, the call will fail. To ensure that all keys in the path exist, you must call <b>RtlCreateRegistryKey</b> once for each key in the path. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561754">RtlCheckRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561829">RtlDeleteRegistryValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562046">RtlQueryRegistryValues</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563034">RtlWriteRegistryValue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>
 

 

