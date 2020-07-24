---
UID: NF:wdm.PcwUnregister
title: PcwUnregister function (wdm.h)
description: The PcwUnregister function unregisters the provider of the specified counter set.
old-location: devtest\pcwunregister.htm
tech.root: devtest
ms.assetid: cf6aeb30-732b-494c-a714-caa6326c0375
ms.date: 02/23/2018
keywords: ["PcwUnregister function"]
ms.keywords: PcwUnregister, PcwUnregister function [Driver Development Tools], devtest.pcwunregister, km_pcw_842b91a3-a846-4d1c-adcd-7e1b3fdf4af5.xml, wdm/PcwUnregister
f1_keywords:
 - "wdm/PcwUnregister"
 - "PcwUnregister"
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PcwUnregister
targetos: Windows
req.typenames: 
---

# PcwUnregister function


## -description


The <b>PcwUnregister</b> function unregisters the provider of the specified counter set. 


## -parameters




### -param Registration [in]

A pointer to the registration being removed.


## -remarks



The <b>PcwUnregister</b> function unregisters the provider of the specified counter-set. Instances owned by the counter-set registration are automatically destroyed. These instances should not be touched by the provider while the counter set is being unregistered, or accessed after the counter set is unregistered.

Before the provider uses this function, the provider must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwregister">PcwRegister</a> function to create a registration.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwregister">PcwRegister</a>
 

 

