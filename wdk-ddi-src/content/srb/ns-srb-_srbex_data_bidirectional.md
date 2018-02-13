---
UID: NS:srb._SRBEX_DATA_BIDIRECTIONAL
title: "_SRBEX_DATA_BIDIRECTIONAL"
author: windows-driver-content
description: The SRBEX_DATA_BIDIRECTIONAL structure contains the extended SRB data for bi-directional transfer commands.
old-location: storage\srbex_data_bidirectional.htm
old-project: storage
ms.assetid: B61247DC-8AC3-4A96-985B-A4CAC232555E
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSRBEX_DATA_BIDIRECTIONAL structure pointer [Storage Devices], storage.srbex_data_bidirectional, storport/SRBEX_DATA_BIDIRECTIONAL, *PSRBEX_DATA_BIDIRECTIONAL, PSRBEX_DATA_BIDIRECTIONAL, SRBEX_DATA_BIDIRECTIONAL structure [Storage Devices], storport/PSRBEX_DATA_BIDIRECTIONAL, _SRBEX_DATA_BIDIRECTIONAL, SRBEX_DATA_BIDIRECTIONAL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: srb.h
req.include-header: Storport.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	HeaderDef
apilocation:
-	Storport.h
apiname:
-	SRBEX_DATA_BIDIRECTIONAL
product: Windows
targetos: Windows
req.typenames: "*PSRBEX_DATA_BIDIRECTIONAL, SRBEX_DATA_BIDIRECTIONAL"
req.product: Windows 10 or later.
---

# _SRBEX_DATA_BIDIRECTIONAL structure


## -description


The <b>SRBEX_DATA_BIDIRECTIONAL</b> structure contains the extended SRB data for bi-directional transfer commands.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _SRBEX_DATA_BIDIRECTIONAL {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  ULONG               DataInTransferLength;
  ULONG               Reserved1;
  PVOID POINTER_ALIGN DataInBuffer;
} SRBEX_DATA_BIDIRECTIONAL, *PSRBEX_DATA_BIDIRECTIONAL;
````


## -struct-fields




### -field Type

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeBidirectional</b>.


### -field Length

Length of the data in this structure, in bytes, starting with the <b>DataInTransferLength</b> member. Set to SRBEX_DATA_BIDIRECTIONAL_LENGTH.


### -field DataInTransferLength

Length of the data present  in the <b>DataInBuffer</b> member.


### -field Reserved1

This member is reserved. Set to 0.


### -field DataInBuffer

A pointer to the buffer that contains the data sent from the device.


## -see-also

<a href="..\srb\ns-srb-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRBEX_DATA_BIDIRECTIONAL structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

