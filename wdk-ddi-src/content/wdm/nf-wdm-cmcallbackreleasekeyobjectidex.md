---
UID: NF:wdm.CmCallbackReleaseKeyObjectIDEx
title: CmCallbackReleaseKeyObjectIDEx function
author: windows-driver-content
description: The CmCallbackReleaseKeyObjectIDEx routine frees an object name string obtained from the CmCallbackGetKeyObjectIDEx routine.
old-location: kernel\cmcallbackreleasekeyobjectidex.htm
old-project: kernel
ms.assetid: 3361DAEF-AC2A-401B-80E8-0220F191587C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: CmCallbackReleaseKeyObjectIDEx, wdm/CmCallbackReleaseKeyObjectIDEx, CmCallbackReleaseKeyObjectIDEx routine [Kernel-Mode Driver Architecture], kernel.cmcallbackreleasekeyobjectidex
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	CmCallbackReleaseKeyObjectIDEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# CmCallbackReleaseKeyObjectIDEx function


## -description


The <b>CmCallbackReleaseKeyObjectIDEx</b> routine frees an object name string obtained from the <a href="..\wdm\nf-wdm-cmcallbackgetkeyobjectidex.md">CmCallbackGetKeyObjectIDEx</a> routine.


## -syntax


````
VOID CmCallbackReleaseKeyObjectIDEx(
   PCUNICODE_STRING ObjectName
);
````


## -parameters




### -param ObjectName

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the object name string. The driver previously obtained this pointer by calling <a href="..\wdm\nf-wdm-cmcallbackgetkeyobjectidex.md">CmCallbackGetKeyObjectIDEx</a>.


## -returns


None.



## -see-also

<a href="..\wdm\nf-wdm-cmcallbackgetkeyobjectidex.md">CmCallbackGetKeyObjectIDEx</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CmCallbackReleaseKeyObjectIDEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

