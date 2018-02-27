---
UID: NF:storport.ScsiPortReadRegisterUshort
title: ScsiPortReadRegisterUshort macro
author: windows-driver-content
description: The ScsiPortReadRegisterUshort routine reads a USHORT value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisterushort.htm
old-project: storage
ms.assetid: 192a525e-6a42-4bd0-9c50-d13741469a48
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ScsiPortReadRegisterUshort, ScsiPortReadRegisterUshort routine [Storage Devices], scsiprt_342c6cc3-090e-4bea-be54-1a52f50d8276.xml, srb/ScsiPortReadRegisterUshort, storage.scsiportreadregisterushort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Miniport.h, Scsi.h, Storport.h
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Scsiport.lib
-	Scsiport.dll
apiname:
-	ScsiPortReadRegisterUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# ScsiPortReadRegisterUshort macro


## -description


The <b>ScsiPortReadRegisterUshort</b> routine reads a USHORT value from the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
USHORT ScsiPortReadRegisterUshort(
  _In_ PUSHORT Register
);
````


## -parameters




### -param Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


## -remarks



<b>ScsiPortReadRegisterUshort</b> ensures that the data is transferred correctly.




## -see-also

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortReadRegisterUshort routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

