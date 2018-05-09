---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.ConnectedStandby
title: IWDTFSystemAction2::ConnectedStandby
author: windows-driver-content
description: Puts the system into Connected Standby state and exits Connected Standby state after the desired time has passed. This method only works on a computer that supports Always On Always Connected (AOAC).
old-location: dtf\iwdtfsystemaction2_connectedstandby.htm
old-project: dtf
ms.assetid: 11d774b1-2af9-453e-b53e-c232d84bcbee
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: ConnectedStandby, ConnectedStandby method [Windows Device Testing Framework], ConnectedStandby method [Windows Device Testing Framework],IWDTFSystemAction2 interface, IWDTFSystemAction2 interface [Windows Device Testing Framework],ConnectedStandby method, IWDTFSystemAction2.ConnectedStandby, IWDTFSystemAction2::ConnectedStandby, Microsoft.WDTF.IWDTFSystemAction2.ConnectedStandby, Microsoft::WDTF::IWDTFSystemAction2::ConnectedStandby, dtf.iwdtfsystemaction2_connectedstandby, wdtfsystemaction/IWDTFSystemAction2::ConnectedStandby
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.ConnectedStandby
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSystemAction2::ConnectedStandby


## -description


Puts the system into Connected Standby state and 
    exits Connected Standby state after the desired time has passed. This method
    only works on a computer that supports  Always On Always Connected (AOAC). 


## -parameters




### -param TimeInMs [in]

Specifies how much time (in milliseconds) has to pass 
    before exiting Connected Standby.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439302">IWDTFSystemAction2</a>
 

 

