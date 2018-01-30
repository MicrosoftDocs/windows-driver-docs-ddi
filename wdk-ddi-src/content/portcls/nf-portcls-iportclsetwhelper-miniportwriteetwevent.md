---
UID: NF:portcls.IPortClsEtwHelper.MiniportWriteEtwEvent
title: IPortClsEtwHelper::MiniportWriteEtwEvent method
author: windows-driver-content
description: The MiniportWriteEtwEvent method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event.
old-location: audio\iportclsetwhelper_miniportwriteetwevent.htm
old-project: audio
ms.assetid: 7E0C1140-35AA-424F-8229-21B4F4E1EBDF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortClsEtwHelper::MiniportWriteEtwEvent, IPortClsEtwHelper, MiniportWriteEtwEvent method [Audio Devices], IPortClsEtwHelper interface, audio.iportclsetwhelper_miniportwriteetwevent, MiniportWriteEtwEvent method [Audio Devices], portcls/IPortClsEtwHelper::MiniportWriteEtwEvent, IPortClsEtwHelper interface [Audio Devices], MiniportWriteEtwEvent method, MiniportWriteEtwEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IPortClsEtwHelper.MiniportWriteEtwEvent
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsEtwHelper::MiniportWriteEtwEvent method


## -description


The <code>MiniportWriteEtwEvent</code> method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event.


## -syntax


````
NTSTATUS MiniportWriteEtwEvent(
  [in] EPcMiniportEngineEvent miniportEventType,
  [in] ULONGLONG              pvData1,
  [in] ULONGLONG              pvData2,
  [in] ULONGLONG              ulData3,
  [in] ULONGLONG              ulData4
);
````


## -parameters




### -param miniportEventType [in]

An <a href="..\portcls\ne-portcls-epcminiportengineevent.md">EPcMiniportEngineEvent</a> enumerated value that provides additional error information for reporting glitching errors.


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

<a href="..\portcls\nn-portcls-iportclsetwhelper.md">IPortClsEtwHelper</a>

<a href="..\portcls\ne-portcls-epcminiportengineevent.md">EPcMiniportEngineEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsEtwHelper::MiniportWriteEtwEvent method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

