---
UID: NS:ntddcdrm._CDROM_SIMPLE_OPC_INFO
title: "_CDROM_SIMPLE_OPC_INFO"
author: windows-driver-content
description: The CDROM_SIMPLE_OPC_INFO structure is the only input for the IOCTL_CDROM_SEND_OPC_INFORMATION I/O control code.
old-location: storage\cdrom_simple_opc_info.htm
old-project: storage
ms.assetid: CE6D2C98-C4C3-4D76-B49E-1B9344B88666
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_SIMPLE_OPC_INFO, CDROM_SIMPLE_OPC_INFO, CDROM_SIMPLE_OPC_INFO structure [Storage Devices], PCDROM_SIMPLE_OPC_INFO, PCDROM_SIMPLE_OPC_INFO structure pointer [Storage Devices], _CDROM_SIMPLE_OPC_INFO, ntddcdrm/CDROM_SIMPLE_OPC_INFO, ntddcdrm/PCDROM_SIMPLE_OPC_INFO, storage.cdrom_simple_opc_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	Ntddcdrm.h
api_name:
-	CDROM_SIMPLE_OPC_INFO
product: Windows
targetos: Windows
req.typenames: CDROM_SIMPLE_OPC_INFO, *PCDROM_SIMPLE_OPC_INFO
---

# _CDROM_SIMPLE_OPC_INFO structure


## -description


The <b>CDROM_SIMPLE_OPC_INFO</b> structure is the only input for the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_send_opc_information.md">IOCTL_CDROM_SEND_OPC_INFORMATION</a> I/O control code. 


## -syntax


````
typedef struct _CDROM_SIMPLE_OPC_INFO {
   CDROM_OPC_INFO_TYPE    RequestType;
  BOOLEAN                 Exclude0;
  BOOLEAN                 Exclude1;
} CDROM_SIMPLE_OPC_INFO, *PCDROM_SIMPLE_OPC_INFO;
````


## -struct-fields




### -field RequestType

The request type defined in the <a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_opc_info_type.md">CDROM_OPC_INFO_TYPE</a> enumeration.


### -field Exclude0

Exclude layer 0 from OPC.


### -field Exclude1

Exclude layer 1 from OPC.


## -remarks



The  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_send_opc_information.md">IOCTL_CDROM_SEND_OPC_INFORMATION</a> IOCTL is a wrapper for the SEND OPC INFORMATION command of the Multimedia Commands (MMC) specification. The <b>Exclude0</b> and <b>Exclude1</b> fields of the <b>CDROM_SIMPLE_OPC_INFO</b> structure map directly to the corresponding SEND OPC INFORMATION fields.




## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_send_opc_information.md">IOCTL_CDROM_SEND_OPC_INFORMATION</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_simple_opc_info.md">CDROM_SIMPLE_OPC_INFO</a>



<a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_opc_info_type.md">CDROM_OPC_INFO_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_SIMPLE_OPC_INFO structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

