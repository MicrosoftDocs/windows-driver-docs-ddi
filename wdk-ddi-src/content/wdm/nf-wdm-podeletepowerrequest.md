---
UID: NF:wdm.PoDeletePowerRequest
title: PoDeletePowerRequest function
author: windows-driver-content
description: The PoDeletePowerRequest routine deletes a power request object.
old-location: kernel\podeletepowerrequest.htm
tech.root: kernel
ms.assetid: 21298d5b-e99f-470f-a352-65da2d91b81e
ms.date: 04/30/2018
ms.keywords: PoDeletePowerRequest, PoDeletePowerRequest routine [Kernel-Mode Driver Architecture], kernel.podeletepowerrequest, portn_a0e21464-039d-4619-b9d5-f67bf2d7273b.xml, wdm/PoDeletePowerRequest
ms.topic: function
req.header: wdm.h
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoDeletePowerRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoDeletePowerRequest function


## -description


The <b>PoDeletePowerRequest</b> routine deletes a power request object.


## -parameters




### -param PowerRequest [in, out]

A pointer to a power request object that was created by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559663">PoCreatePowerRequest</a> routine.


## -returns



None




## -remarks



The driver must delete the power request object before it deletes the device object that was used to create the power request object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559663">PoCreatePowerRequest</a>
 

 

