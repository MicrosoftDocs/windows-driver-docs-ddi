---
UID: NF:wdm.PoDeletePowerRequest
title: PoDeletePowerRequest function
author: windows-driver-content
description: The PoDeletePowerRequest routine deletes a power request object.
old-location: kernel\podeletepowerrequest.htm
old-project: kernel
ms.assetid: 21298d5b-e99f-470f-a352-65da2d91b81e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.podeletepowerrequest, PoDeletePowerRequest, portn_a0e21464-039d-4619-b9d5-f67bf2d7273b.xml, PoDeletePowerRequest routine [Kernel-Mode Driver Architecture], wdm/PoDeletePowerRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PoDeletePowerRequest
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoDeletePowerRequest function


## -description


The <b>PoDeletePowerRequest</b> routine deletes a power request object.


## -syntax


````
VOID PoDeletePowerRequest(
  _Inout_ PVOID PowerRequest
);
````


## -parameters




#### - PowerRequest [in, out]

A pointer to a power request object that was created by the <a href="..\wdm\nf-wdm-pocreatepowerrequest.md">PoCreatePowerRequest</a> routine.


## -returns


None



## -remarks


The driver must delete the power request object before it deletes the device object that was used to create the power request object.



## -see-also

<a href="..\wdm\nf-wdm-pocreatepowerrequest.md">PoCreatePowerRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoDeletePowerRequest routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

