---
UID: NS:ntddcdrm._CDROM_SIMPLE_OPC_INFO
title: "_CDROM_SIMPLE_OPC_INFO"
author: windows-driver-content
description: The CDROM_SIMPLE_OPC_INFO structure is the only input for the IOCTL_CDROM_SEND_OPC_INFORMATION I/O control code.
old-location: storage\cdrom_simple_opc_info.htm
tech.root: storage
ms.assetid: CE6D2C98-C4C3-4D76-B49E-1B9344B88666
ms.date: 3/29/2018
ms.keywords: "*PCDROM_SIMPLE_OPC_INFO, CDROM_SIMPLE_OPC_INFO, CDROM_SIMPLE_OPC_INFO structure [Storage Devices], PCDROM_SIMPLE_OPC_INFO, PCDROM_SIMPLE_OPC_INFO structure pointer [Storage Devices], _CDROM_SIMPLE_OPC_INFO, ntddcdrm/CDROM_SIMPLE_OPC_INFO, ntddcdrm/PCDROM_SIMPLE_OPC_INFO, storage.cdrom_simple_opc_info"
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
product:
- Windows
targetos: Windows
req.typenames: CDROM_SIMPLE_OPC_INFO, *PCDROM_SIMPLE_OPC_INFO
---

# _CDROM_SIMPLE_OPC_INFO structure


## -description


The <b>CDROM_SIMPLE_OPC_INFO</b> structure is the only input for the <a href="https://msdn.microsoft.com/library/windows/hardware/gg441243">IOCTL_CDROM_SEND_OPC_INFORMATION</a> I/O control code. 


## -struct-fields




### -field RequestType

The request type defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/gg441230">CDROM_OPC_INFO_TYPE</a> enumeration.


### -field Exclude0

Exclude layer 0 from OPC.


### -field Exclude1

Exclude layer 1 from OPC.


## -remarks



The  <a href="https://msdn.microsoft.com/library/windows/hardware/gg441243">IOCTL_CDROM_SEND_OPC_INFORMATION</a> IOCTL is a wrapper for the SEND OPC INFORMATION command of the Multimedia Commands (MMC) specification. The <b>Exclude0</b> and <b>Exclude1</b> fields of the <b>CDROM_SIMPLE_OPC_INFO</b> structure map directly to the corresponding SEND OPC INFORMATION fields.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/gg441230">CDROM_OPC_INFO_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/gg441237">CDROM_SIMPLE_OPC_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/gg441243">IOCTL_CDROM_SEND_OPC_INFORMATION</a>
 

 

