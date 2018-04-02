---
UID: NF:wdm.PcwRegister
title: PcwRegister function
author: windows-driver-content
description: The PcwRegister function registers the caller as a provider of the specified counter set.
old-location: devtest\pcwregister.htm
old-project: devtest
ms.assetid: 40fdb77c-bd6b-4ecd-a9c8-fd5e5b2adc80
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PcwRegister, PcwRegister function [Driver Development Tools], devtest.pcwregister, km_pcw_5204b626-3251-4c63-bd89-be1470980960.xml, wdm/PcwRegister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PcwRegister
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PcwRegister function


## -description


The <b>PcwRegister</b> function registers the caller as a provider of the specified counter set.


## -parameters




### -param Registration [out]

A pointer to a PCW_REGISTRATION structure. Receives the handle to the newly allocated registration. The pointer is referenced before the function returns. The caller is responsible to dereference the pointer.


### -param Info [in]

A pointer to a PCW_REGISTRATION_INFORMATION structure that contains the details about the counter set being registered.


## -returns



This function returns one of the following values:

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
The counter set is successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The <i>Version</i> specified by <i>Info</i> does not match the supported value for this version of Windows.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The number of the counters exposed by this registration exceeds the space available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
There is not enough space available to allocate memory for the counters

</td>
</tr>
</table>
 




## -remarks



The provider calls this function to create a new registration. The registration is added to the counter set's registration list. All the input arguments are captured so that the caller does not have to keep a copy of them.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550326">PcwUnregister</a>
 

 

