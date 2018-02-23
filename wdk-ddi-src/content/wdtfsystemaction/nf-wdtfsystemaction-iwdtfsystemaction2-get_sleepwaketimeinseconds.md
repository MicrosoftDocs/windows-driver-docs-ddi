---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.get_SleepWakeTimeInSeconds
title: IWDTFSystemAction2::get_SleepWakeTimeInSeconds method
author: windows-driver-content
description: Gets or sets the time in seconds when the system will wake from the sleep state.
old-location: dtf\iwdtfsystemaction2_sleepwaketimeinseconds.htm
old-project: dtf
ms.assetid: 90b9742d-966b-4502-92ec-670c663d9a76
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDTFSystemAction2::get_SleepWakeTimeInSeconds, wdtfsystemaction/IWDTFSystemAction2::get_SleepWakeTimeInSeconds, SleepWakeTimeInSeconds property [Windows Device Testing Framework], SleepWakeTimeInSeconds property [Windows Device Testing Framework], IWDTFSystemAction2 interface, wdtfsystemaction/IWDTFSystemAction2::put_SleepWakeTimeInSeconds, Microsoft::WDTF::IWDTFSystemAction2::SleepWakeTimeInSeconds, IWDTFSystemAction2.SleepWakeTimeInSeconds, IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], SleepWakeTimeInSeconds property, IWDTFSystemAction2::put_SleepWakeTimeInSeconds, dtf.iwdtfsystemaction2_sleepwaketimeinseconds, wdtfsystemaction/IWDTFSystemAction2::SleepWakeTimeInSeconds, Microsoft.WDTF.IWDTFSystemAction2.SleepWakeTimeInSeconds, get_SleepWakeTimeInSeconds
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFSystemAction.Interop.dll
req.type-library: 
req.lib: wdtfsystemaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFSystemAction.Interop.dll
apiname:
-	IWDTFSystemAction2.SleepWakeTimeInSeconds
-	IWDTFSystemAction2.get_SleepWakeTimeInSeconds
-	IWDTFSystemAction2.put_SleepWakeTimeInSeconds
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::get_SleepWakeTimeInSeconds method


## -description


Gets or sets the time in seconds when the system will wake from the sleep state.

This property is read/write.


## -syntax


````
HRESULT put_SleepWakeTimeInSeconds(
  [in]          LONG nWakeTimeInSeconds
);

HRESULT get_SleepWakeTimeInSeconds(
  [out, retval] LONG *pnWakeTimeInSeconds
);
````


## -parameters


## -see-also

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::SleepWakeTimeInSeconds property%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

