---
UID: NF:wdm.PoUnregisterPowerSettingCallback
title: PoUnregisterPowerSettingCallback function
author: windows-driver-content
description: The PoUnregisterPowerSettingCallback routine unregisters a power-setting callback routine that a driver previously registered by calling the PoRegisterPowerSettingCallback routine.
old-location: kernel\pounregisterpowersettingcallback.htm
old-project: kernel
ms.assetid: 900db70b-4cdb-41e7-a4cf-0dc435b9fe7d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PoUnregisterPowerSettingCallback, PoUnregisterPowerSettingCallback routine [Kernel-Mode Driver Architecture], kernel.pounregisterpowersettingcallback, portn_52c569d1-68d0-48a4-88e7-c2ffb27aa530.xml, wdm/PoUnregisterPowerSettingCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	PoUnregisterPowerSettingCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoUnregisterPowerSettingCallback function


## -description


The <b>PoUnregisterPowerSettingCallback</b> routine unregisters a power-setting callback routine that a driver previously registered by calling the <a href="..\wdm\nf-wdm-poregisterpowersettingcallback.md">PoRegisterPowerSettingCallback</a> routine.


## -syntax


````
NTSTATUS PoUnregisterPowerSettingCallback(
  _Inout_ PVOID Handle
);
````


## -parameters




### -param Handle [in, out]

A handle to a callback routine that a driver registered by calling <b>PoRegisterPowerSettingCallback</b>.


## -returns



<b>PoUnregisterPowerSettingCallback</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callback routine was unregistered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Handle</i> value is not a valid handle to a power setting callback routine.

</td>
</tr>
</table>
 




## -remarks



A driver calls <b>PoUnregisterPowerSettingCallback</b> to unregister a power setting callback routine that the driver previously registered by calling <b>PoRegisterPowerSettingCallback</b>.

A driver must call <b>PoUnregisterPowerSettingCallback</b> to unregister each callback routine that it previously registered. All callback routines registered by a driver should be unregistered in the <i>Unload</i> routine of the driver.




## -see-also

<a href="..\wdm\nf-wdm-poregisterpowersettingcallback.md">PoRegisterPowerSettingCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoUnregisterPowerSettingCallback routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

