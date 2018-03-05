---
UID: NS:hbapiwmi._ScsiReadCapacity_OUT
title: "_ScsiReadCapacity_OUT"
author: windows-driver-content
description: The ScsiReadCapacity_OUT structure is used to report the output data of the ScsiReadCapacity WMI method to the WMI client.
old-location: storage\scsireadcapacity_out2.htm
old-project: storage
ms.assetid: bf295061-42d6-4f2e-a39e-9bac440b0d93
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PScsiReadCapacity_OUT, PScsiReadCapacity_OUT, PScsiReadCapacity_OUT structure pointer [Storage Devices], ScsiReadCapacity_OUT, ScsiReadCapacity_OUT structure [Storage Devices], _ScsiReadCapacity_OUT, hbapiwmi/PScsiReadCapacity_OUT, hbapiwmi/ScsiReadCapacity_OUT, storage.scsireadcapacity_out2, structs-Fibre_b362afaf-6cf2-4e2b-9239-11d7fdec3d74.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hbapiwmi.h
api_name:
-	ScsiReadCapacity_OUT
product: Windows
targetos: Windows
req.typenames: ScsiReadCapacity_OUT, *PScsiReadCapacity_OUT
---

# _ScsiReadCapacity_OUT structure


## -description


The ScsiReadCapacity_OUT structure is used to report the output data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564890">ScsiReadCapacity</a> WMI method to the WMI client.


## -syntax


````
typedef struct _ScsiReadCapacity_OUT {
  ULONG HBAStatus;
  ULONG ResponseBufferSize;
  ULONG SenseBufferSize;
  UCHAR ScsiStatus;
  UCHAR ResponseBuffer[1];
  UCHAR SenseBuffer[1];
} ScsiReadCapacity_OUT, *PScsiReadCapacity_OUT;
````


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation. 


### -field ResponseBufferSize

Indicates the size in bytes of the buffer that will hold the results of the read capacity command. 


### -field SenseBufferSize

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the read capacity command. 


### -field ScsiStatus

Contains the status of the SCSI read capacity command. 


### -field ResponseBuffer

Contains the results of the SCSI read capacity command. 


#### - SenseBuffer

Contains the SCSI sense data that results from the SCSI read capacity command. 


## -remarks



The WMI tool suite generates a declaration of the ScsiReadCapacity_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564890">ScsiReadCapacity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiReadCapacity_OUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

