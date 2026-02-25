---
UID: NS:iddcx.IDARG_IN_I2C_TRANSMIT_AND_RECEIVE
title: IDARG_IN_I2C_TRANSMIT_AND_RECEIVE (iddcx.h)
description: Gives information about the I2C data being transmitted and received by the OS.
prerelease: true
old-location:
tech.root: display
ms.date: 02/17/2026
keywords: ["IDARG_IN_I2C_TRANSMIT_AND_RECEIVE structure"]
ms.keywords: IDARG_IN_I2C_TRANSMIT_AND_RECEIVE, IDARG_IN_I2C_TRANSMIT_AND_RECEIVE structure [Display Devices], iddcx/IDARG_IN_I2C_TRANSMIT_AND_RECEIVE
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
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
req.typenames: 
f1_keywords:
 - IDARG_IN_I2C_TRANSMIT_AND_RECEIVE
 - iddcx/IDARG_IN_I2C_TRANSMIT_AND_RECEIVE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_I2C_TRANSMIT_AND_RECEIVE
---

# IDARG_IN_I2C_TRANSMIT_AND_RECEIVE structure

## -description

Gives information about the I2C data being transmitted ane received by the OS.

## -struct-fields

### -field TransmitSevenBitI2CAddress

[in] The address of the I2C device to which data will be transmitted.

### -field TransmitDataSizeInBytes

[in] The size, in bytes, of the buffer pointed to by **pTransmitData**. This parameter must be between 1 and 64, inclusively.

### -field pTransmitData

[in] A pointer to a buffer that holds the data to be transmitted.

### -field ReceiveSevenBitI2CAddress

[in] The address of the I2C device from which data will be received.

### -field ReceiveFlags

[in] Flags for the receive operation.

### -field ReceiveDataSizeInBytes

[in] The size, in bytes, of the buffer pointed to by **pReceiveData**.

### -field pReceiveData

[out] A pointer to a buffer that receives the data.

## -see-also

[EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE](nc-iddcx-evt_idd_cx_monitor_i2c_transmit_and_receive.md)