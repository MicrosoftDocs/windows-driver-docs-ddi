---
UID: NS:ptpusd._PTP_VENDOR_DATA_OUT
title: _PTP_VENDOR_DATA_OUT (ptpusd.h)
description: The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device.
old-location: image\ptp_vendor_data_out.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["PTP_VENDOR_DATA_OUT structure"]
ms.keywords: "*PPTP_VENDOR_DATA_OUT, PPTP_VENDOR_DATA_OUT, PPTP_VENDOR_DATA_OUT structure pointer [Imaging Devices], PTP_VENDOR_DATA_OUT, PTP_VENDOR_DATA_OUT structure [Imaging Devices], _PTP_VENDOR_DATA_OUT, image.ptp_vendor_data_out, ptpusd/PPTP_VENDOR_DATA_OUT, ptpusd/PTP_VENDOR_DATA_OUT, wiastrct_032c0aa0-aec8-440d-b528-de1b739d2e1d.xml"
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
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
f1_keywords:
 - _PTP_VENDOR_DATA_OUT
 - ptpusd/_PTP_VENDOR_DATA_OUT
 - PPTP_VENDOR_DATA_OUT
 - ptpusd/PPTP_VENDOR_DATA_OUT
 - PTP_VENDOR_DATA_OUT
 - ptpusd/PTP_VENDOR_DATA_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ptpusd.h
api_name:
 - _PTP_VENDOR_DATA_OUT
 - PPTP_VENDOR_DATA_OUT
 - PTP_VENDOR_DATA_OUT
---

# _PTP_VENDOR_DATA_OUT structure


## -description

The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device.

## -struct-fields

### -field ResponseCode

Specifies the response code. For more information, see [ISO 15740:2013 *Photography − Electronic still picture imaging − Picture Transfer Protocol (PTP) for Digital Still Photography Devices*](https://www.imaging.org/site/IST/IST/Standards/PTP_Standards.aspx).

### -field SessionId

Specifies the session ID. This member is not currently used by the PTP driver and should be set to 0.

### -field TransactionId

Specifies the transaction ID. This member is not currently used by the PTP driver and should be set to 0.

### -field Params

Is an array consisting of PTP_MAX_PARAMS (defined in *Ptpusd.h*) elements, representing the parameters of the response.

### -field VendorReadData

Is an array containing an (optional) first byte to read from the device.

## -remarks

See [Vendor-Extended Commands](/windows-hardware/drivers/image/vendor-extended-commands) for more information and example code that uses this structure.

For more information about the opcodes used in the **OpCode** member, see [ISO 15740:2013 *Photography − Electronic still picture imaging − Picture Transfer Protocol (PTP) for Digital Still Photography Devices*](https://www.imaging.org/site/IST/IST/Standards/PTP_Standards.aspx).

## -see-also

[PTP_VENDOR_DATA_IN](./ns-ptpusd-_ptp_vendor_data_in.md)

