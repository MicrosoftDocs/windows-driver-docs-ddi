---
UID: NS:hbapiwmi._SendLIRR_OUT
title: _SendLIRR_OUT (hbapiwmi.h)
description: The SendLIRR_OUT structure is used to report the output parameter data of the SendLIRR WMI method to the WMI client.
old-location: storage\sendlirr_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SendLIRR_OUT structure"]
ms.keywords: "*PSendLIRR_OUT, PSendLIRR_OUT, PSendLIRR_OUT structure pointer [Storage Devices], SendLIRR_OUT, SendLIRR_OUT structure [Storage Devices], _SendLIRR_OUT, hbapiwmi/PSendLIRR_OUT, hbapiwmi/SendLIRR_OUT, storage.sendlirr_out, structs-Fibre_193ae454-313d-4ada-a161-39c403226edf.xml"
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
targetos: Windows
req.typenames: SendLIRR_OUT, *PSendLIRR_OUT
f1_keywords:
 - _SendLIRR_OUT
 - hbapiwmi/_SendLIRR_OUT
 - PSendLIRR_OUT
 - hbapiwmi/PSendLIRR_OUT
 - SendLIRR_OUT
 - hbapiwmi/SendLIRR_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _SendLIRR_OUT
 - PSendLIRR_OUT
 - SendLIRR_OUT
---

# _SendLIRR_OUT structure


## -description

The SendLIRR_OUT structure is used to report the output parameter data of the <a href="/windows-hardware/drivers/storage/sendlirr">SendLIRR</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field TotalRspBufferSize

Contains the size in bytes of the results of the LIRR command.

### -field ActualRspBufferSize

Contains the size in bytes of the data that was actually retrieved.

### -field RspBuffer

Contains the results of the LIRR command.

## -remarks

The WMI tool suite generates a declaration of the SendLIRR_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/sendlirr">SendLIRR</a>

