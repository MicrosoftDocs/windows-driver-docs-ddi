---
UID: NS:hbapiwmi._SendSRL_OUT
title: _SendSRL_OUT (hbapiwmi.h)
description: The SendSRL_OUT structure is used to report the output parameter data of the SendSRL WMI method to the WMI client.
old-location: storage\sendsrl_out.htm
tech.root: storage
ms.assetid: f7a08e0e-cbb1-4ec5-96c6-dade9d298d0a
ms.date: 03/29/2018
keywords: ["SendSRL_OUT structure"]
ms.keywords: "*PSendSRL_OUT, PSendSRL_OUT, PSendSRL_OUT structure pointer [Storage Devices], SendSRL_OUT, SendSRL_OUT structure [Storage Devices], _SendSRL_OUT, hbapiwmi/PSendSRL_OUT, hbapiwmi/SendSRL_OUT, storage.sendsrl_out, structs-Fibre_4cef4091-719d-457e-aeca-d3ab10b23344.xml"
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
req.typenames: SendSRL_OUT, *PSendSRL_OUT
f1_keywords:
 - _SendSRL_OUT
 - hbapiwmi/_SendSRL_OUT
 - PSendSRL_OUT
 - hbapiwmi/PSendSRL_OUT
 - SendSRL_OUT
 - hbapiwmi/SendSRL_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SendSRL_OUT
---

# _SendSRL_OUT structure


## -description

The SendSRL_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendsrl">SendSRL</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field TotalRspBufferSize

Contains the size in bytes of the results of the SRL command.

### -field ActualRspBufferSize

Contains the size in bytes of the data that was actually retrieved.

### -field RspBuffer

Contains the results of the SRL command.

## -remarks

The WMI tool suite generates a declaration of the SendSRL_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendsrl">SendSRL</a>

