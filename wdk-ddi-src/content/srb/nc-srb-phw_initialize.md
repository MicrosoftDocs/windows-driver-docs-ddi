---
UID: NC:srb.PHW_INITIALIZE
title: PHW_INITIALIZE
author: windows-driver-content
description: The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.
old-location: storage\phw_initialize.htm
old-project: storage
ms.assetid: dd678196-62f6-4c27-845f-a9b52c663e2a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.phw_initialize, (*PHW_INITIALIZE) callback function [Storage Devices], (*PHW_INITIALIZE), srb/(*PHW_INITIALIZE), ide_minikr_95bb126d-6d4c-4091-b2fa-6b891d587186.xml
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
-	(*PHW_INITIALIZE)
product: Windows
targetos: Windows
req.typenames: *PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_INITIALIZE callback


## -description


The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs. 


## -prototype


````
typedef BOOLEAN (*PHW_INITIALIZE)(
  _In_ PVOID DeviceExtension 
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area. 


## -returns


If the operation succeeds, the initialization routine returns <b>TRUE</b>. Otherwise, the initialize routine returns <b>FALSE</b>. 



## -remarks


The initialization routine for both SCSI and StorPort miniport drivers are declared using this prototype. 

For more information about the SCSI miniport driver initialization routine see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557302">HwScsiInitialize</a>. 

For more information about the miniport driver initialization routine that is used with the StorPort driver see <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a>. 



## -see-also

<a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557302">HwScsiInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_INITIALIZE callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

