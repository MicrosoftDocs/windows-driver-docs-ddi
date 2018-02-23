---
UID: NC:srb.PHW_TIMER
title: PHW_TIMER
author: windows-driver-content
description: The PHW_TIMER routine prototype declares a SCSI miniport driver's timer routine.
old-location: storage\phw_timer.htm
old-project: storage
ms.assetid: 8f537ddb-ba94-4423-95a8-6497710d234f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.phw_timer, (*PHW_TIMER) callback function [Storage Devices], (*PHW_TIMER), srb/(*PHW_TIMER), ide_minikr_55cc9012-04fa-434c-b2b9-d24bbd1d1404.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	srb.h
apiname:
-	(*PHW_TIMER)
product: Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_TIMER callback


## -description


The PHW_TIMER routine prototype declares a SCSI miniport driver's timer routine.


## -prototype


````
typedef VOID (*PHW_TIMER)(
  _In_ PVOID DeviceExtension 
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area. 


## -returns



None




## -remarks



The SCSI miniport driver's timer routine, <a href="..\srb\nc-srb-phw_timer.md">HwScsiTimer</a>, is called after the interval specified when the miniport driver called <b>ScsiPortNotification</b> with the <b>RequestTimerCall</b><i>NotificationType</i> value.

Miniport drivers that work with the StorPort driver do not use this timer routine. 




## -see-also

<a href="..\srb\nc-srb-phw_timer.md">HwScsiTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_TIMER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

