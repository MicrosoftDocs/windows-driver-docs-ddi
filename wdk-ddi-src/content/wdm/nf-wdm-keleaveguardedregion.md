---
UID: NF:wdm.KeLeaveGuardedRegion
title: KeLeaveGuardedRegion function
author: windows-driver-content
description: The KeLeaveGuardedRegion routine exits a guarded region entered by KeEnterGuardedRegion.
old-location: kernel\keleaveguardedregion.htm
old-project: kernel
ms.assetid: 189a3589-0d43-4f87-b889-f1f092190ffa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeLeaveGuardedRegion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeLeaveGuardedRegion
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: GuardedRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeLeaveGuardedRegion function



## -description
The <b>KeLeaveGuardedRegion</b> routine exits a guarded region entered by <b>KeEnterGuardedRegion</b>.



## -syntax

````
VOID KeLeaveGuardedRegion(void);
````


## -parameters


## -returns
None

None

None


## -remarks
Guarded regions can be nested, so APCs are only reenabled once the thread exists the outermost guarded region.

For more information about guarded regions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542925">Critical Regions and Guarded Regions</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-keenterguardedregion.md">KeEnterGuardedRegion</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeLeaveGuardedRegion routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

