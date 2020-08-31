---
UID: NS:hbapiwmi._SendCTPassThru_OUT
title: _SendCTPassThru_OUT (hbapiwmi.h)
description: The SendCTPassThru_OUT structure is used to report the output parameter data of the SendCTPassThru WMI method to the WMI client.
old-location: storage\sendctpassthru_out.htm
tech.root: storage
ms.assetid: f9340f0d-4f70-4751-b339-de11ee13a469
ms.date: 03/29/2018
keywords: ["SendCTPassThru_OUT structure"]
ms.keywords: "*PSendCTPassThru_OUT, PSendCTPassThru_OUT, PSendCTPassThru_OUT structure pointer [Storage Devices], SendCTPassThru_OUT, SendCTPassThru_OUT structure [Storage Devices], _SendCTPassThru_OUT, hbapiwmi/PSendCTPassThru_OUT, hbapiwmi/SendCTPassThru_OUT, storage.sendctpassthru_out, structs-Fibre_f795d452-fb3f-4236-a543-d0f80f94c14f.xml"
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
req.typenames: SendCTPassThru_OUT, *PSendCTPassThru_OUT
f1_keywords:
 - _SendCTPassThru_OUT
 - hbapiwmi/_SendCTPassThru_OUT
 - PSendCTPassThru_OUT
 - hbapiwmi/PSendCTPassThru_OUT
 - SendCTPassThru_OUT
 - hbapiwmi/SendCTPassThru_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SendCTPassThru_OUT
---

# _SendCTPassThru_OUT structure


## -description

The SendCTPassThru_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendctpassthru">SendCTPassThru</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field TotalResponseBufferCount

Contains the size in bytes of the results common transport (CT) command.

### -field ActualResponseBufferCount

Contains the size in bytes of the data that was actually retrieved.

### -field ResponseBuffer

Contains the results of the common transport command.

## -remarks

The WMI tool suite generates a declaration of the SendCTPassThru_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendctpassthru">SendCTPassThru</a>

