---
UID: NE:ntddcdrm._CDROM_OPC_INFO_TYPE
title: _CDROM_OPC_INFO_TYPE (ntddcdrm.h)
description: The CDROM_OPC_INFO_TYPE enumeration is a member of the CDROM_SIMPLE_OPC_INFO structure. It defines the Optimum Power Calibration (OPC) request that is used as input to the IOCTL_CDROM_SEND_OPC_INFORMATION I/O control request.
old-location: storage\cdrom_opc_info_type.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["CDROM_OPC_INFO_TYPE enumeration"]
ms.keywords: "*PCDROM_OPC_INFO_TYPE, CDROM_OPC_INFO_TYPE, CDROM_OPC_INFO_TYPE enumeration [Storage Devices], PCDROM_OPC_INFO_TYPE, PCDROM_OPC_INFO_TYPE enumeration pointer [Storage Devices], SimpleOpcInfo, _CDROM_OPC_INFO_TYPE, ntddcdrm/CDROM_OPC_INFO_TYPE, ntddcdrm/PCDROM_OPC_INFO_TYPE, ntddcdrm/SimpleOpcInfo, storage.cdrom_opc_info_type"
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
targetos: Windows
req.typenames: CDROM_OPC_INFO_TYPE, *PCDROM_OPC_INFO_TYPE
f1_keywords:
 - _CDROM_OPC_INFO_TYPE
 - ntddcdrm/_CDROM_OPC_INFO_TYPE
 - PCDROM_OPC_INFO_TYPE
 - ntddcdrm/PCDROM_OPC_INFO_TYPE
 - CDROM_OPC_INFO_TYPE
 - ntddcdrm/CDROM_OPC_INFO_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdrm.h
api_name:
 - CDROM_OPC_INFO_TYPE
---

# _CDROM_OPC_INFO_TYPE enumeration


## -description

The <b>CDROM_OPC_INFO_TYPE</b>  enumeration is a member of the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_simple_opc_info">CDROM_SIMPLE_OPC_INFO</a> structure. It defines the Optimum Power Calibration (OPC) request that is used as input to the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_send_opc_information">IOCTL_CDROM_SEND_OPC_INFORMATION</a> I/O control request.

## -enum-fields

### -field SimpleOpcInfo

Specifies the wrapper for the SEND OPC INFORMATION command from the Multimedia Commands (MMC) specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_simple_opc_info">CDROM_SIMPLE_OPC_INFO</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_send_opc_information">IOCTL_CDROM_SEND_OPC_INFORMATION</a>
