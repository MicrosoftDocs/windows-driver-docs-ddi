---
UID: NF:wdm.PcwUnregister
title: PcwUnregister function
author: windows-driver-content
description: The PcwUnregister function unregisters the provider of the specified counter set.
old-location: devtest\pcwunregister.htm
old-project: devtest
ms.assetid: cf6aeb30-732b-494c-a714-caa6326c0375
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PcwUnregister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcwUnregister
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PcwUnregister function



## -description
The <b>PcwUnregister</b> function unregisters the provider of the specified counter set. 



## -syntax

````
VOID PcwUnregister(
  _In_ PPCW_REGISTRATION Registration
);
````


## -parameters

### -param Registration [in]

A pointer to the registration being removed.


## -returns
None


## -remarks
The <b>PcwUnregister</b> function unregisters the provider of the specified counter-set. Instances owned by the counter-set registration are automatically destroyed. These instances should not be touched by the provider while the counter set is being unregistered, or accessed after the counter set is unregistered.

Before the provider uses this function, the provider must call the <a href="..\wdm\nf-wdm-pcwregister.md">PcwRegister</a> function to create a registration.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-pcwregister.md">PcwRegister</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PcwUnregister function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

