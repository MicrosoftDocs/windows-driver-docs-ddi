---
UID: NF:srb.ScsiPortWritePortUchar
title: ScsiPortWritePortUchar function
author: windows-driver-content
description: The ScsiPortWritePortUchar routine transfers an unsigned byte to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportuchar.htm
old-project: storage
ms.assetid: aba28a55-d7bc-4f75-ac87-4148cb1b4cfb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ScsiPortWritePortUchar
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
req.alt-api: ScsiPortWritePortUchar
req.alt-loc: Scsiport.lib,Scsiport.dll
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
req.typenames: *PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# ScsiPortWritePortUchar function



## -description
The <b>ScsiPortWritePortUchar</b> routine transfers an unsigned byte to the HBA.



## -syntax

````
VOID ScsiPortWritePortUchar(
  _In_ PUCHAR Port,
  _In_ UCHAR  Value
);
````


## -parameters

### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Value [in]

Specifies the value to be written to the HBA's I/O port.


## -returns
None


## -remarks


## -see-also
<dl>
<dt>
<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortWritePortUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

