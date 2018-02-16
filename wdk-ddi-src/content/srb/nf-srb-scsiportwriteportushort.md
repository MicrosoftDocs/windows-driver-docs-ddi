---
UID: NF:srb.ScsiPortWritePortUshort
title: ScsiPortWritePortUshort function
author: windows-driver-content
description: The ScsiPortWritePortUshort routine transfers a USHORT value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportushort.htm
old-project: storage
ms.assetid: 4b1accd8-5dbe-47d6-822e-1997a6ab5082
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: srb/ScsiPortWritePortUshort, storage.scsiportwriteportushort, ScsiPortWritePortUshort, ScsiPortWritePortUshort routine [Storage Devices], scsiprt_e7e27190-3f51-4ede-9b4d-fcc437f46d17.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
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
-	ScsiPortWritePortUshort
product: Windows
targetos: Windows
req.typenames: "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product: Windows 10 or later.
---

# ScsiPortWritePortUshort function


## -description


The <b>ScsiPortWritePortUshort</b> routine transfers a USHORT value to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID ScsiPortWritePortUshort(
  _In_ PUSHORT Port,
  _In_ USHORT  Value
);
````


## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Value [in]

Specifies the value to be written to the HBA's I/O port.


## -returns



None




## -see-also

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortWritePortUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

