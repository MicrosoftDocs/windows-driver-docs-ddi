---
UID: NS:ptpusd._PTP_VENDOR_DATA_IN
title: _PTP_VENDOR_DATA_IN (ptpusd.h)
description: The PTP_VENDOR_DATA_IN structure contains information about an arbitrary command that an application issues to the device.
old-location: image\ptp_vendor_data_in.htm
tech.root: image
ms.assetid: 896209d0-d545-495b-b743-98c0b9d976ff
ms.date: 05/03/2018
keywords: ["PTP_VENDOR_DATA_IN structure"]
ms.keywords: "*PPTP_VENDOR_DATA_IN, PPTP_VENDOR_DATA_IN, PPTP_VENDOR_DATA_IN structure pointer [Imaging Devices], PTP_VENDOR_DATA_IN, PTP_VENDOR_DATA_IN structure [Imaging Devices], _PTP_VENDOR_DATA_IN, image.ptp_vendor_data_in, ptpusd/PPTP_VENDOR_DATA_IN, ptpusd/PTP_VENDOR_DATA_IN, wiastrct_b0ebb671-78d9-4224-8bde-893fb0afc9f8.xml"
f1_keywords:
 - "ptpusd/PTP_VENDOR_DATA_IN"
 - "PTP_VENDOR_DATA_IN"
req.header: ptpusd.h
req.include-header: Ptpusd.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ptpusd.h
api_name:
- PTP_VENDOR_DATA_IN
targetos: Windows
req.typenames: PTP_VENDOR_DATA_IN, *PPTP_VENDOR_DATA_IN
---

# _PTP_VENDOR_DATA_IN structure

## -description

The PTP_VENDOR_DATA_IN structure contains information about an arbitrary command that an application issues to the device.

## -struct-fields

### -field OpCode

Specifies the command opcode. For more information, see [ISO 15740:2013 *Photography − Electronic still picture imaging − Picture Transfer Protocol (PTP) for Digital Still Photography Devices*](https://www.imaging.org/site/IST/IST/Standards/PTP_Standards.aspx).

### -field SessionId

Specifies the session ID. This member is not currently used by the PTP driver and should be set to 0.

### -field TransactionId

Specifies the transaction ID. This member is not currently used by the PTP driver and should be set to 0.

### -field Params

Is an array consisting of PTP_MAX_PARAMS (defined in *Ptpusd.h*) elements, representing the parameters of the command.

### -field NumParams

Specifies the actual number of elements in the **Params** array.

### -field NextPhase

Indicates whether to read data from the device, write data to the device, or neither. This member can be set to one of the following values:

| Value | Meaning |
| --- | --- |
| PTP_NEXTPHASE_NO_DATA | No data is to be read from or written to the device. |
| PTP_NEXTPHASE_READ_DATA | Read data from the device. |
| PTP_NEXTPHASE_WRITE_DATA | Write data to the device. |

### -field VendorWriteData

Is an array containing an (optional) first byte to write to the device.

## -remarks

See [Vendor-Extended Commands](https://docs.microsoft.com/windows-hardware/drivers/image/vendor-extended-commands) for more information and example code that uses this structure.

For more information about the opcodes used in the **OpCode** member, see [ISO 15740:2013 *Photography − Electronic still picture imaging − Picture Transfer Protocol (PTP) for Digital Still Photography Devices*](https://www.imaging.org/site/IST/IST/Standards/PTP_Standards.aspx).

## -see-also

[PTP_VENDOR_DATA_OUT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ptpusd/ns-ptpusd-_ptp_vendor_data_out)
