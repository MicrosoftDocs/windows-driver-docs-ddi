---
UID: NF:wdm.CmCallbackReleaseKeyObjectIDEx
title: CmCallbackReleaseKeyObjectIDEx function (wdm.h)
description: The CmCallbackReleaseKeyObjectIDEx routine frees an object name string obtained from the CmCallbackGetKeyObjectIDEx routine.
old-location: kernel\cmcallbackreleasekeyobjectidex.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["CmCallbackReleaseKeyObjectIDEx function"]
ms.keywords: CmCallbackReleaseKeyObjectIDEx, CmCallbackReleaseKeyObjectIDEx routine [Kernel-Mode Driver Architecture], kernel.cmcallbackreleasekeyobjectidex, wdm/CmCallbackReleaseKeyObjectIDEx
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CmCallbackReleaseKeyObjectIDEx
 - wdm/CmCallbackReleaseKeyObjectIDEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CmCallbackReleaseKeyObjectIDEx
---

# CmCallbackReleaseKeyObjectIDEx function


## -description

The <b>CmCallbackReleaseKeyObjectIDEx</b> routine frees an object name string obtained from the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmcallbackgetkeyobjectidex">CmCallbackGetKeyObjectIDEx</a> routine.

## -parameters

### -param ObjectName

A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the object name string. The driver previously obtained this pointer by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmcallbackgetkeyobjectidex">CmCallbackGetKeyObjectIDEx</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmcallbackgetkeyobjectidex">CmCallbackGetKeyObjectIDEx</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
