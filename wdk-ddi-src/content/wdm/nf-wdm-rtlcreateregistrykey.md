---
UID: NF:wdm.RtlCreateRegistryKey
title: RtlCreateRegistryKey function
author: windows-driver-content
description: The RtlCreateRegistryKey routine adds a key object in the registry along a given relative path.
old-location: kernel\rtlcreateregistrykey.htm
old-project: kernel
ms.assetid: 2214acc8-b24a-4db4-9ce3-f639291428f2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlCreateRegistryKey routine [Kernel-Mode Driver Architecture], wdm/RtlCreateRegistryKey, RtlCreateRegistryKey, k109_9a163bcc-501d-453b-b426-a4267d04135c.xml, kernel.rtlcreateregistrykey
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlCreateRegistryKey
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlCreateRegistryKey function


## -description


The <b>RtlCreateRegistryKey</b> routine adds a key object in the registry along a given relative path.


## -syntax


````
NTSTATUS RtlCreateRegistryKey(
  _In_ ULONG RelativeTo,
  _In_ PWSTR Path
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
</table>
 


### -param Path [in]

Specifies the registry path according to the <i>RelativeTo</i> value. 


## -returns



<b>RtlCreateRegistryKey</b> returns STATUS_SUCCESS if the key is created. 




## -remarks



<b>RtlCreateRegistryKey</b> creates only the keys that you specify. It does not create missing keys in the path to the specified key. If any keys in the path are missing, the call will fail. To ensure that all keys in the path exist, you must call <b>RtlCreateRegistryKey</b> once for each key in the path. 




## -see-also

<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>



<a href="..\wdm\nf-wdm-rtldeleteregistryvalue.md">RtlDeleteRegistryValue</a>



<a href="..\wdm\nf-wdm-rtlcheckregistrykey.md">RtlCheckRegistryKey</a>



<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>



<a href="..\wdm\nf-wdm-rtlwriteregistryvalue.md">RtlWriteRegistryValue</a>



<a href="..\wdm\nf-wdm-rtlqueryregistryvalues.md">RtlQueryRegistryValues</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCreateRegistryKey routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

