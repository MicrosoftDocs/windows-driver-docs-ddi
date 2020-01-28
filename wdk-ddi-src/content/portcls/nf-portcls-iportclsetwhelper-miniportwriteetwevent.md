---
UID: NF:portcls.IPortClsEtwHelper.MiniportWriteEtwEvent
title: IPortClsEtwHelper::MiniportWriteEtwEvent (portcls.h)
description: The MiniportWriteEtwEvent method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event.
old-location: audio\iportclsetwhelper_miniportwriteetwevent.htm
tech.root: audio
ms.assetid: 7E0C1140-35AA-424F-8229-21B4F4E1EBDF
ms.date: 05/08/2018
ms.keywords: IPortClsEtwHelper interface [Audio Devices],MiniportWriteEtwEvent method, IPortClsEtwHelper.MiniportWriteEtwEvent, IPortClsEtwHelper::MiniportWriteEtwEvent, MiniportWriteEtwEvent, MiniportWriteEtwEvent method [Audio Devices], MiniportWriteEtwEvent method [Audio Devices],IPortClsEtwHelper interface, audio.iportclsetwhelper_miniportwriteetwevent, portcls/IPortClsEtwHelper::MiniportWriteEtwEvent
f1_keywords:
 - "portcls/IPortClsEtwHelper.MiniportWriteEtwEvent"
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IPortClsEtwHelper.MiniportWriteEtwEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsEtwHelper::MiniportWriteEtwEvent


## -description


The <code>MiniportWriteEtwEvent</code> method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event.


## -parameters




### -param miniportEventType [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ne-portcls-epcminiportengineevent">EPcMiniportEngineEvent</a> enumerated value that provides additional error information for reporting glitching errors.


### -param pvData1 [in]

Data parameter.


### -param pvData2 [in]

Data parameter.


### -param ulData3 [in]

Data parameter.


### -param ulData4 [in]

Data parameter.


## -returns



<b>MiniportWriteEtwEvent</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ne-portcls-epcminiportengineevent">EPcMiniportEngineEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportclsetwhelper">IPortClsEtwHelper</a>
 

 

