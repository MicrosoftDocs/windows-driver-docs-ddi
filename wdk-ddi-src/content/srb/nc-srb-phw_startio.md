---
UID: NC:srb.PHW_STARTIO
title: PHW_STARTIO
author: windows-driver-content
description: The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.
old-location: storage\phw_startio.htm
old-project: storage
ms.assetid: 1b177ef5-2b58-425e-9b9a-428bbe15de69
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.phw_startio, (*PHW_STARTIO) callback function [Storage Devices], (*PHW_STARTIO), srb/(*PHW_STARTIO), ide_minikr_16fd699a-4cb9-4741-9e50-3fa8177f49f2.xml
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
-	(*PHW_STARTIO)
product: Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_STARTIO callback


## -description


The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs. 


## -prototype


````
typedef BOOLEAN (*PHW_STARTIO)(
  _In_ PVOID               DeviceExtension ,
  _In_ PSCSI_REQUEST_BLOCK Srb 
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area. 


### -param Srb [in]

Pointer to the SCSI request block to be started. 


## -returns


The start I/O routine returns <b>TRUE</b> to acknowledge receipt of the SCSI request block (SRB). If the start I/O routine does not receive a well-formed SRB, it returns <b>FALSE</b>.



## -remarks


The start routine for both SCSI and StorPort miniport drivers are declared using this prototype. 

For more information about the SCSI miniport driver's start I/O routine see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557323">HwScsiStartIo</a>. 

For more information about the miniport driver's start I/O routine that is used with the StorPort driver see <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557323">HwScsiStartIo</a>

<a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_STARTIO callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

