---
UID: NF:srb.ScsiPortConvertUlongToPhysicalAddress
title: ScsiPortConvertUlongToPhysicalAddress function
author: windows-driver-content
description: The ScsiPortConvertUlongToPhysicalAddress routine extends a given ULONG address into a value of type SCSI_PHYSICAL_ADDRESS.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportconvertulongtophysicaladdress.htm
old-project: storage
ms.assetid: 98d491f8-eeb5-4152-9bb6-fffabcba0360
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.scsiportconvertulongtophysicaladdress, scsiprt_9dc27865-55c2-4599-913c-babe77c62af9.xml, ScsiPortConvertUlongToPhysicalAddress, ScsiPortConvertUlongToPhysicalAddress routine [Storage Devices], srb/ScsiPortConvertUlongToPhysicalAddress
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
-	ScsiPortConvertUlongToPhysicalAddress
product: Windows
targetos: Windows
req.typenames: "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product: Windows 10 or later.
---

# ScsiPortConvertUlongToPhysicalAddress function


## -description


The <b>ScsiPortConvertUlongToPhysicalAddress</b> routine extends a given ULONG address into a value of type SCSI_PHYSICAL_ADDRESS.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
SCSI_PHYSICAL_ADDRESS ScsiPortConvertUlongToPhysicalAddress(
  _In_ ULONG_PTR UlongAddress
);
````


## -parameters




### -param UlongAddress [in]

Specifies a value of type ULONG.


## -returns


<b>ScsiPortConvertUlongToPhysicalAddress</b> returns the converted SCSI_PHYSICAL_ADDRESS.



## -see-also

<a href="..\srb\nf-srb-scsiportgetvirtualaddress.md">ScsiPortGetVirtualAddress</a>

<a href="..\srb\ns-srb-_access_range.md">ACCESS_RANGE</a>

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortConvertUlongToPhysicalAddress routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

