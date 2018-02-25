---
UID: NF:wdm.ExSetFirmwareEnvironmentVariable
title: ExSetFirmwareEnvironmentVariable function
author: windows-driver-content
description: The ExSetFirmwareEnvironmentVariable routine sets the value of the specified system firmware environment variable.
old-location: kernel\exsetfirmwareenvironmentvariable.htm
old-project: kernel
ms.assetid: 04447D92-EB9E-400B-A018-E70B186EA3DB
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, ExSetFirmwareEnvironmentVariable, ExSetFirmwareEnvironmentVariable routine [Kernel-Mode Driver Architecture], F, S, V, a, b, e, i, kernel.exsetfirmwareenvironmentvariable, l, m, n, o, r, t, v, w, wdm/ExSetFirmwareEnvironmentVariable, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
-	ExSetFirmwareEnvironmentVariable
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExSetFirmwareEnvironmentVariable function


## -description


The <b>ExSetFirmwareEnvironmentVariable</b> routine sets the value of the specified system firmware environment variable.


## -syntax


````
NTSTATUS ExSetFirmwareEnvironmentVariable(
  _In_ PUNICODE_STRING VariableName,
  _In_ LPGUID          VendorGuid,
  _In_ PVOID           Value,
  _In_ ULONG           ValueLength,
  _In_ ULONG           Attributes
);
````


## -parameters




### -param VariableName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the specified environment variable.


### -param VendorGuid [in]

A pointer to a GUID that identifies the vendor associated with the specified environment variable. Environment variables are grouped into namespaces based on their vendor GUIDs. Some hardware platforms might not support vendor GUIDs. On these platforms, all variables are grouped into one, common namespace, and the <i>VendorGuid</i> parameter is ignored.


### -param Value [in]

A pointer to a caller-allocated buffer that contains the data value to write to the specified environment variable.


### -param ValueLength [in]

The size, in bytes, of the data value contained in the <i>Value</i> buffer.


### -param Attributes [in]

The attributes to assign to the specified environment variable. The VARIABLE_ATTRIBUTE_NON_VOLATILE attribute bit must be set or this call will fail. For more information about the attribute bits that are defined for this parameter, see Remarks in <a href="..\wdm\nf-wdm-exgetfirmwareenvironmentvariable.md">ExGetFirmwareEnvironmentVariable</a>.


## -returns



<b>ExSetFirmwareEnvironmentVariable</b> returns STATUS_SUCCESS if it is successful. Possible return values include the following error status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Available system resources are insufficient to complete the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This routine is not supported on this platform.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The firmware returned an unrecognized error.

</td>
</tr>
</table>
 




## -remarks



The caller requires the system environment privilege (SE_SYSTEM_ENVIRONMENT_PRIVILEGE) to use this routine.

System firmware environment variables contain data values that are passed between the boot firmware environment implemented in the hardware platform and the operating-system loaders and other software that runs in the firmware environment.  For more information, see Remarks in <a href="..\wdm\nf-wdm-exgetfirmwareenvironmentvariable.md">ExGetFirmwareEnvironmentVariable</a>.

If you create a backup datastore, you can use the  <a href="..\wdm\nf-wdm-exgetfirmwareenvironmentvariable.md">ExGetFirmwareEnvironmentVariable</a> routine to save all the boot settings for the platform. Later, you can use <b>ExSetFirmwareEnvironmentVariable</b> to restore these settings if needed.

<b>ExSetFirmwareEnvironmentVariable</b> is the kernel-mode equivalent of the Win32 <a href="https://msdn.microsoft.com/42117632-61aa-4f83-abe1-c08f40cf3f0a">SetFirmwareEnvironmentVariable</a> function.




## -see-also

<a href="https://msdn.microsoft.com/42117632-61aa-4f83-abe1-c08f40cf3f0a">SetFirmwareEnvironmentVariable</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-exgetfirmwareenvironmentvariable.md">ExGetFirmwareEnvironmentVariable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExSetFirmwareEnvironmentVariable routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

