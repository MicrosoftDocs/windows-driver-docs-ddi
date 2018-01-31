---
UID: NF:wdm.KeDeregisterProcessorChangeCallback
title: KeDeregisterProcessorChangeCallback function
author: windows-driver-content
description: The KeDeregisterProcessorChangeCallback routine unregisters a callback function that was previously registered with the operating system by calling the KeRegisterProcessorChangeCallback routine.
old-location: kernel\kederegisterprocessorchangecallback.htm
old-project: kernel
ms.assetid: 69b0f360-dfe5-4e1f-bdcb-0f908ed129a7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_d3e135a0-4eca-4879-97cc-946ad22693db.xml, kernel.kederegisterprocessorchangecallback, wdm/KeDeregisterProcessorChangeCallback, KeDeregisterProcessorChangeCallback routine [Kernel-Mode Driver Architecture], KeDeregisterProcessorChangeCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeDeregisterProcessorChangeCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeDeregisterProcessorChangeCallback function


## -description


The <b>KeDeregisterProcessorChangeCallback</b> routine unregisters a callback function that was previously registered with the operating system by calling the <a href="..\wdm\nf-wdm-keregisterprocessorchangecallback.md">KeRegisterProcessorChangeCallback</a> routine.


## -syntax


````
VOID KeDeregisterProcessorChangeCallback(
  _In_ PVOID CallbackHandle
);
````


## -parameters




#### - CallbackHandle [in]

The callback registration handle that was returned by the <a href="..\wdm\nf-wdm-keregisterprocessorchangecallback.md">KeRegisterProcessorChangeCallback</a> routine when the callback function was registered with the operating system. 


## -returns


None



## -remarks


A device driver calls the <a href="..\wdm\nf-wdm-keregisterprocessorchangecallback.md">KeRegisterProcessorChangeCallback</a> routine to register a callback function with the operating system so that the operating system will notify the driver when a new processor is added to the hardware partition. When the device driver no longer needs to receive notification when new processors are added to the hardware paritition, it calls the <b>KeDeregisterProcessorChangeCallback</b> routine to unregister the callback function. A callback function that has been registered for notification of processor changes must be unregistered before the device driver is unloaded from the operating system. 



## -see-also

<a href="..\wdm\nf-wdm-keregisterprocessorchangecallback.md">KeRegisterProcessorChangeCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeDeregisterProcessorChangeCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

