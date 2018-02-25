---
UID: NE:ntddcdrm._CDROM_OPC_INFO_TYPE
title: "_CDROM_OPC_INFO_TYPE"
author: windows-driver-content
description: The CDROM_OPC_INFO_TYPE enumeration is a member of the CDROM_SIMPLE_OPC_INFO structure. It defines the Optimum Power Calibration (OPC) request that is used as input to the IOCTL_CDROM_SEND_OPC_INFORMATION I/O control request.
old-location: storage\cdrom_opc_info_type.htm
old-project: storage
ms.assetid: 447D225C-4B73-4567-81E3-950EBC802F84
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PCDROM_OPC_INFO_TYPE, ,, C, CDROM_OPC_INFO_TYPE, CDROM_OPC_INFO_TYPE enumeration [Storage Devices], D, E, F, I, M, N, O, P, PCDROM_OPC_INFO_TYPE, PCDROM_OPC_INFO_TYPE enumeration pointer [Storage Devices], R, SimpleOpcInfo, T, Y, _, _CDROM_OPC_INFO_TYPE, ntddcdrm/CDROM_OPC_INFO_TYPE, ntddcdrm/PCDROM_OPC_INFO_TYPE, ntddcdrm/SimpleOpcInfo, storage.cdrom_opc_info_type"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddcdrm.h
apiname:
-	CDROM_OPC_INFO_TYPE
product: Windows
targetos: Windows
req.typenames: CDROM_OPC_INFO_TYPE, *PCDROM_OPC_INFO_TYPE
---

# _CDROM_OPC_INFO_TYPE enumeration


## -description


The <b>CDROM_OPC_INFO_TYPE</b>  enumeration is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_simple_opc_info.md">CDROM_SIMPLE_OPC_INFO</a> structure. It defines the Optimum Power Calibration (OPC) request that is used as input to the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_send_opc_information.md">IOCTL_CDROM_SEND_OPC_INFORMATION</a> I/O control request. 


## -syntax


````
typedef enum _CDROM_OPC_INFO_TYPE { 
  SimpleOpcInfo  = 1
} CDROM_OPC_INFO_TYPE, *PCDROM_OPC_INFO_TYPE;
````


## -enum-fields




### -field SimpleOpcInfo

Specifies the wrapper for the SEND OPC INFORMATION command from the Multimedia Commands (MMC) specification.


## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_simple_opc_info.md">CDROM_SIMPLE_OPC_INFO</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_send_opc_information.md">IOCTL_CDROM_SEND_OPC_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_OPC_INFO_TYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

