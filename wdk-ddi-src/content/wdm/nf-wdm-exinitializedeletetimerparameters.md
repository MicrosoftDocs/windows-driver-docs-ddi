---
UID: NF:wdm.ExInitializeDeleteTimerParameters
title: ExInitializeDeleteTimerParameters function
author: windows-driver-content
description: The ExInitializeDeleteTimerParameters routine initializes an EXT_DELETE_PARAMETERS structure.
old-location: kernel\exinitializedeletetimerparameters.htm
old-project: kernel
ms.assetid: 2AD23AE1-05FF-44AF-807F-1ABD9D0D24DA
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExInitializeDeleteTimerParameters, ExInitializeDeleteTimerParameters routine [Kernel-Mode Driver Architecture], wdm/ExInitializeDeleteTimerParameters, kernel.exinitializedeletetimerparameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level.
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Wdm.h
apiname: 
-	ExInitializeDeleteTimerParameters
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInitializeDeleteTimerParameters function


## -description


The <b>ExInitializeDeleteTimerParameters</b> routine initializes an <a href="..\wdm\ns-wdm-_ext_delete_parameters.md">EXT_DELETE_PARAMETERS</a> structure.


## -syntax


````
VOID ExInitializeDeleteTimerParameters(
   PEXT_DELETE_PARAMETERS Parameters
);
````


## -parameters




### -param Parameters

A pointer to the <b>EXT_DELETE_PARAMETERS</b> structure that is to be initialized.


## -returns


None.



## -remarks


Your driver must call <b>ExInitializeDeleteTimerParameters</b> to initialize an <b>EXT_DELETE_PARAMETERS</b> structure before the driver passes this structure to the <a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a> routine. For more information about the member values that <b>ExInitializeDeleteTimerParameters</b> writes to the members of this structure, see <a href="..\wdm\ns-wdm-_ext_delete_parameters.md">EXT_DELETE_PARAMETERS</a>.



## -see-also

<a href="..\wdm\ns-wdm-_ext_delete_parameters.md">EXT_DELETE_PARAMETERS</a>

<a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInitializeDeleteTimerParameters routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

