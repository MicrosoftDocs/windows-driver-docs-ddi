---
UID: NF:wdm.PcwCloseInstance
title: PcwCloseInstance function (wdm.h)
description: The PcwCloseInstance function closes the specified instance of the counter set.
old-location: devtest\pcwcloseinstance.htm
tech.root: devtest
ms.assetid: a577a116-9e5e-42d3-aac0-a6b90131ad9d
ms.date: 02/23/2018
ms.keywords: PcwCloseInstance, PcwCloseInstance function [Driver Development Tools], devtest.pcwcloseinstance, km_pcw_f30288bf-ff25-46fd-b058-74294fc03278.xml, wdm/PcwCloseInstance
ms.topic: function
f1_keywords:
 - "wdm/PcwCloseInstance"
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
- PcwCloseInstance
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcwCloseInstance function


## -description


The <b>PcwCloseInstance</b> function closes the specified instance of the counter set. 


## -parameters




### -param Instance [in]

A pointer to the instance of the counter set to close. 


## -returns



None




## -remarks



Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pcwcreateinstance">PcwCreateInstance</a> function to create an instance of a registered counter set. You cannot call <b>PcwCloseInstance</b> if you have already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pcwunregister">PcwUnregister</a>. When you unregister the counter set, the instances are closed for you.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pcwcreateinstance">PcwCreateInstance</a>
 

 

