---
UID: NE:wdm._PCW_CALLBACK_TYPE
title: _PCW_CALLBACK_TYPE (wdm.h)
description: The PCW_CALLBACK_TYPE enumeration defines the notification type to send to the registered provider of the counter set. A provider passes a pointer to this enumeration as a parameter to the PcwCallback function.
old-location: devtest\pcw_callback_type.htm
tech.root: devtest
ms.assetid: 92f7a980-509a-44af-b480-fa8c212f4ac6
ms.date: 02/23/2018
ms.keywords: "*PPCW_CALLBACK_TYPE, PCW_CALLBACK_TYPE, PCW_CALLBACK_TYPE enumeration [Driver Development Tools], PPCW_CALLBACK_TYPE, PPCW_CALLBACK_TYPE enumeration pointer [Driver Development Tools], PcwCallbackAddCounter, PcwCallbackCollectData, PcwCallbackEnumerateInstances, PcwCallbackRemoveCounter, _PCW_CALLBACK_TYPE, devtest.pcw_callback_type, km_pcw_39199484-e1fb-4d3b-9bab-27d8d880a9bf.xml, wdm/PCW_CALLBACK_TYPE, wdm/PPCW_CALLBACK_TYPE, wdm/PcwCallbackAddCounter, wdm/PcwCallbackCollectData, wdm/PcwCallbackEnumerateInstances, wdm/PcwCallbackRemoveCounter"
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCW_CALLBACK_TYPE
product:
- Windows
targetos: Windows
req.typenames: PCW_CALLBACK_TYPE, *PPCW_CALLBACK_TYPE
---

# _PCW_CALLBACK_TYPE enumeration


## -description


The <b>PCW_CALLBACK_TYPE</b> enumeration defines the notification type to send to the registered provider of the counter set. A provider passes a pointer to this enumeration as a parameter to the <a href="https://msdn.microsoft.com/5058fc17-1016-45bc-a6ea-5e2458824e7b">PcwCallback</a> function. 


## -enum-fields




### -field PcwCallbackAddCounter

The provider is asked to add an instance of the counter set.


### -field PcwCallbackRemoveCounter

The provider is asked to remove an instance of the counter set.


### -field PcwCallbackEnumerateInstances

The provider is asked to enumerate instances of the counter set.


### -field PcwCallbackCollectData

The provider is asked to collect data from an instance of the counter set.


## -see-also




<a href="https://msdn.microsoft.com/5058fc17-1016-45bc-a6ea-5e2458824e7b">PcwCallback</a>
 

 

