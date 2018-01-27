---
UID: NC:wdm.KIPI_BROADCAST_WORKER
title: KIPI_BROADCAST_WORKER
author: windows-driver-content
description: The IpiGenericCall routine runs simultaneously on all processors.
old-location: kernel\ipigenericcall.htm
old-project: kernel
ms.assetid: 7c4e3d6b-e000-4ac4-b200-966689d05426
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.ipigenericcall, IpiGenericCall routine [Kernel-Mode Driver Architecture], IpiGenericCall, KIPI_BROADCAST_WORKER, KIPI_BROADCAST_WORKER, wdm/IpiGenericCall, DrvrRtns_80b940d9-3d19-4525-af3f-8e4058c57ddc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: Called at IPI_LEVEL.
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Wdm.h
apiname: 
-	IpiGenericCall
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# KIPI_BROADCAST_WORKER callback


## -description


The <i>IpiGenericCall</i> routine runs simultaneously on all processors.


## -prototype


````
KIPI_BROADCAST_WORKER IpiGenericCall;

ULONG_PTR IpiGenericCall(
  _In_ ULONG_PTR Argument
)
{ ... }
````


## -parameters




### -param Argument [in]

Supplies the value that was passed to the <a href="..\wdm\nf-wdm-keipigenericcall.md">KeIpiGenericCall</a> routine that called <i>IpiGenericCall</i>.


## -returns


<i>IpiGenericCall</i> returns a driver-defined value. If <i>IpiGenericCall</i> ran on the same processor that called <b>KeIpiGenericCall</b>, <b>KeIpiGenericCall</b> returns the driver-defined value that <i>IpiGenericCall</i> returns. Otherwise, the value is ignored. 



## -remarks


<i>IpiGenericCall</i> routines run at IRQL = IPI_LEVEL, which is greater than DIRQL for every device. <i>IpiGenericCall</i> routines must satisfy the same restrictions as bug check callback routines. For more information about these restrictions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566401">Writing a Bug Check Callback Routine</a>.



## -see-also

<a href="..\wdm\nf-wdm-keipigenericcall.md">KeIpiGenericCall</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IpiGenericCall routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

