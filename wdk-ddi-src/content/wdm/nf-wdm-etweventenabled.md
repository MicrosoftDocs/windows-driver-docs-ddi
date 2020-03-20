---
UID: NF:wdm.EtwEventEnabled
title: EtwEventEnabled function (wdm.h)
description: The EtwEventEnabled function verifies whether an event is enabled.
old-location: devtest\etweventenabled.htm
tech.root: devtest
ms.assetid: 19aa5905-f611-46e2-8d70-a6cc4649c911
ms.date: 02/23/2018
keywords: ["EtwEventEnabled function"]
ms.keywords: EtwEventEnabled, EtwEventEnabled function [Driver Development Tools], devtest.etweventenabled, etw_km_4a6453a7-cff8-4941-83fd-8184772ef161.xml, wdm/EtwEventEnabled
f1_keywords:
 - "wdm/EtwEventEnabled"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- EtwEventEnabled
product:
- Windows
targetos: Windows
req.typenames: 
---

# EtwEventEnabled function


## -description


The <b>EtwEventEnabled</b> function verifies whether an event is enabled.


## -parameters




### -param RegHandle [in]

A pointer to the event provider registration handle, which is returned by the 
      <b>EtwRegister</b> function if the event provider registration is successful.


### -param EventDescriptor [in]

A pointer to a constant EVENT_DESCRIPTOR. 


## -returns



The <b>EtwEventEnabled</b> function returns <b>TRUE</b> if the 
      event is enabled and <b>FALSE</b> if the event is not enabled.




## -remarks



If logging an event requires additional computing, the <b>EtwEventEnabled</b> 
     function can be used to determine whether the event is going to be logged, which will minimize the overhead when 
     logging is disabled.

If the event descriptor is not available, use the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-etwproviderenabled">EtwProviderEnabled</a> function instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-etwproviderenabled">EtwProviderEnabled</a>
 

 

