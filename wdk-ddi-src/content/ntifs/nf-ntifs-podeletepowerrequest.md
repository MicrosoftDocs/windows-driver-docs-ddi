---
UID: NF:ntifs.PoDeletePowerRequest
title: PoDeletePowerRequest function (ntifs.h)
description: The PoDeletePowerRequest routine deletes a power request object.
old-location: kernel\podeletepowerrequest.htm
tech.root: kernel
ms.assetid: 21298d5b-e99f-470f-a352-65da2d91b81e
ms.date: 04/30/2018
keywords: ["PoDeletePowerRequest function"]
ms.keywords: PoDeletePowerRequest, PoDeletePowerRequest routine [Kernel-Mode Driver Architecture], kernel.podeletepowerrequest, portn_a0e21464-039d-4619-b9d5-f67bf2d7273b.xml, wdm/PoDeletePowerRequest
f1_keywords:
 - "ntifs/PoDeletePowerRequest"
 - "PoDeletePowerRequest"
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoDeletePowerRequest
targetos: Windows
req.typenames: 
---

# PoDeletePowerRequest function


## -description


The <b>PoDeletePowerRequest</b> routine deletes a power request object.


## -parameters




### -param PowerRequest [in, out]

A pointer to a power request object that was created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocreatepowerrequest">PoCreatePowerRequest</a> routine.


## -remarks



The driver must delete the power request object before it deletes the device object that was used to create the power request object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocreatepowerrequest">PoCreatePowerRequest</a>
 

 

