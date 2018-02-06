---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.ConnectedStandby
title: IWDTFSystemAction2::ConnectedStandby method
author: windows-driver-content
description: Puts the system into Connected Standby state and exits Connected Standby state after the desired time has passed. This method only works on a computer that supports Always On Always Connected (AOAC).
old-location: dtf\iwdtfsystemaction2_connectedstandby.htm
old-project: dtf
ms.assetid: 11d774b1-2af9-453e-b53e-c232d84bcbee
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWDTFSystemAction2 interface [Windows Device Testing Framework], ConnectedStandby method, ConnectedStandby, ConnectedStandby method [Windows Device Testing Framework], Microsoft::WDTF::IWDTFSystemAction2::ConnectedStandby, IWDTFSystemAction2, IWDTFSystemAction2::ConnectedStandby, Microsoft.WDTF.IWDTFSystemAction2.ConnectedStandby, dtf.iwdtfsystemaction2_connectedstandby, ConnectedStandby method [Windows Device Testing Framework], IWDTFSystemAction2 interface, wdtfsystemaction/IWDTFSystemAction2::ConnectedStandby
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Desktop
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
-	IWDTFSystemAction2.ConnectedStandby
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::ConnectedStandby method


## -description


Puts the system into Connected Standby state and 
    exits Connected Standby state after the desired time has passed. This method
    only works on a computer that supports  Always On Always Connected (AOAC). 


## -syntax


````
HRESULT ConnectedStandby(
  [in] LONG TimeInMs
);
````


## -parameters




### -param TimeInMs [in]

Specifies how much time (in milliseconds) has to pass 
    before exiting Connected Standby.


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -see-also

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::ConnectedStandby method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

