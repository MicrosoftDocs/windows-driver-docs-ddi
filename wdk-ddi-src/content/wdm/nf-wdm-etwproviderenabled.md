---
UID: NF:wdm.EtwProviderEnabled
title: EtwProviderEnabled function
author: windows-driver-content
description: The EtwProviderEnabled function verifies that a provider is enabled for event logging at a specified level and keyword.
old-location: devtest\etwproviderenabled.htm
old-project: devtest
ms.assetid: 28b0a40e-e8e8-4953-8a3a-f3f1b58ad80f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EtwProviderEnabled, EtwProviderEnabled function [Driver Development Tools], devtest.etwproviderenabled, etw_km_ea4989d3-f349-4dda-9d86-f1b9528ddf1c.xml, wdm/EtwProviderEnabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	EtwProviderEnabled
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# EtwProviderEnabled function


## -description


The <b>EtwProviderEnabled</b> function verifies that a provider is enabled for event logging at a specified level and keyword. 


## -parameters




### -param RegHandle [in]

A pointer to the event provider registration handle, which is returned by the <b>EtwRegister</b> function if the event provider registration is successful.


### -param Level [in]

The level at which the provider is enabled.


### -param Keyword [in]

The keyword that indicates whether the provider is enabled.


## -returns



The function returns <b>TRUE</b> if the provider is enabled and <b>FALSE</b> if the provider is not enabled. 




## -remarks



You can use the <b>EtwProviderEnabled</b> function to verify that the registered provider is enabled for any event by passing in zeros for the <i>Level</i> and <i>Keyword</i> values when you call the function. If any event is enabled, the provider is enabled. 

If an event descriptor is already available, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545590">EtwEventEnabled</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545590">EtwEventEnabled</a>
 

 

