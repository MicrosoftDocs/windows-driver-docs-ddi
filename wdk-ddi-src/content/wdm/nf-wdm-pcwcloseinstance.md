---
UID: NF:wdm.PcwCloseInstance
title: PcwCloseInstance function
author: windows-driver-content
description: The PcwCloseInstance function closes the specified instance of the counter set.
old-location: devtest\pcwcloseinstance.htm
old-project: devtest
ms.assetid: a577a116-9e5e-42d3-aac0-a6b90131ad9d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PcwCloseInstance
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
req.alt-api: PcwCloseInstance
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

# PcwCloseInstance function



## -description
The <b>PcwCloseInstance</b> function closes the specified instance of the counter set. 



## -syntax

````
VOID PcwCloseInstance(
  _In_ PPCW_INSTANCE Instance
);
````


## -parameters

### -param Instance [in]

A pointer to the instance of the counter set to close. 


## -returns
None


## -remarks
Use the <a href="..\wdm\nf-wdm-pcwcreateinstance.md">PcwCreateInstance</a> function to create an instance of a registered counter set. You cannot call <b>PcwCloseInstance</b> if you have already called <a href="..\wdm\nf-wdm-pcwunregister.md">PcwUnregister</a>. When you unregister the counter set, the instances are closed for you.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-pcwcreateinstance.md">PcwCreateInstance</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PcwCloseInstance function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

