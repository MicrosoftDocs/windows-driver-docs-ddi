---
UID: NF:wdm.PoUnregisterPowerSettingCallback
title: PoUnregisterPowerSettingCallback function
description: The PoUnregisterPowerSettingCallback routine unregisters a power-setting callback routine that a driver previously registered by calling the PoRegisterPowerSettingCallback routine.
old-location: kernel\pounregisterpowersettingcallback.htm
tech.root: kernel
ms.assetid: 900db70b-4cdb-41e7-a4cf-0dc435b9fe7d
ms.date: 04/30/2018
ms.keywords: PoUnregisterPowerSettingCallback, PoUnregisterPowerSettingCallback routine [Kernel-Mode Driver Architecture], kernel.pounregisterpowersettingcallback, portn_52c569d1-68d0-48a4-88e7-c2ffb27aa530.xml, wdm/PoUnregisterPowerSettingCallback
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoUnregisterPowerSettingCallback function


## -description


The <b>PoUnregisterPowerSettingCallback</b> routine unregisters a power-setting callback routine that a driver previously registered by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559727">PoRegisterPowerSettingCallback</a> routine.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559727">PoRegisterPowerSettingCallback</a>
 

 

