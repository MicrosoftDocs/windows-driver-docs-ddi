---
UID: NF:wdm.CmCallbackReleaseKeyObjectIDEx
title: CmCallbackReleaseKeyObjectIDEx function (wdm.h)
description: The CmCallbackReleaseKeyObjectIDEx routine frees an object name string obtained from the CmCallbackGetKeyObjectIDEx routine.
old-location: kernel\cmcallbackreleasekeyobjectidex.htm
tech.root: kernel
ms.assetid: 3361DAEF-AC2A-401B-80E8-0220F191587C
ms.date: 04/30/2018
ms.keywords: CmCallbackReleaseKeyObjectIDEx, CmCallbackReleaseKeyObjectIDEx routine [Kernel-Mode Driver Architecture], kernel.cmcallbackreleasekeyobjectidex, wdm/CmCallbackReleaseKeyObjectIDEx
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CmCallbackReleaseKeyObjectIDEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# CmCallbackReleaseKeyObjectIDEx function


## -description


The <b>CmCallbackReleaseKeyObjectIDEx</b> routine frees an object name string obtained from the <a href="https://msdn.microsoft.com/library/windows/hardware/jj215789">CmCallbackGetKeyObjectIDEx</a> routine.


## -parameters




### -param ObjectName

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the object name string. The driver previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/jj215789">CmCallbackGetKeyObjectIDEx</a>.


## -returns



None.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj215789">CmCallbackGetKeyObjectIDEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

