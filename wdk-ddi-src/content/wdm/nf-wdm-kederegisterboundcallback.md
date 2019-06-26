---
UID: NF:wdm.KeDeregisterBoundCallback
title: KeDeregisterBoundCallback function (wdm.h)
description: The KeDeregisterBoundCallback routine deregisters a user-mode bound exception callback registered by KeRegisterBoundCallback.
old-location: kernel\kederegisterboundcallback.htm
tech.root: kernel
ms.assetid: 697709D4-DBB7-4CB4-83A1-89E8BAFD68DA
ms.date: 04/30/2018
ms.keywords: KeDeregisterBoundCallback, KeDeregisterBoundCallback routine [Kernel-Mode Driver Architecture], kernel.kederegisterboundcallback, wdm/KeDeregisterBoundCallback
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeDeregisterBoundCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeDeregisterBoundCallback function


## -description


The <b>KeDeregisterBoundCallback</b> routine deregisters a user-mode bound exception callback registered by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keregisterboundcallback">KeRegisterBoundCallback</a>.


## -parameters




### -param Handle [in]

Specifies the value returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keregisterboundcallback">KeRegisterBoundCallback</a> when the callback was registered. 


## -returns



The <b>KeDeregisterBoundCallback</b> routine returns STATUS_SUCCESS if the callback is successfully removed. It returns STATUS_INVALID_HANDLE if no callback matching the provided <i>Handle</i> value is found.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keregisterboundcallback">KeRegisterBoundCallback</a>
 

 

