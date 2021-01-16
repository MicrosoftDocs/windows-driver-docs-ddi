---
UID: NS:dispmprt._DXGK_I2C_INTERFACE
title: _DXGK_I2C_INTERFACE (dispmprt.h)
description: The DXGK_I2C_INTERFACE structure contains pointers to functions in the I2C interface, which is implemented by the display miniport driver.
old-location: display\dxgk_i2c_interface.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGK_I2C_INTERFACE structure"]
ms.keywords: "*PDXGK_I2C_INTERFACE, DXGK_I2C_INTERFACE, DXGK_I2C_INTERFACE structure [Display Devices], DmStructs_59985b59-bb86-459c-8bd2-2b6124a6b9bb.xml, PDXGK_I2C_INTERFACE, PDXGK_I2C_INTERFACE structure pointer [Display Devices], _DXGK_I2C_INTERFACE, display.dxgk_i2c_interface, dispmprt/DXGK_I2C_INTERFACE, dispmprt/PDXGK_I2C_INTERFACE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXGK_I2C_INTERFACE, *PDXGK_I2C_INTERFACE
f1_keywords:
 - _DXGK_I2C_INTERFACE
 - dispmprt/_DXGK_I2C_INTERFACE
 - PDXGK_I2C_INTERFACE
 - dispmprt/PDXGK_I2C_INTERFACE
 - DXGK_I2C_INTERFACE
 - dispmprt/DXGK_I2C_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_I2C_INTERFACE
 - PDXGK_I2C_INTERFACE
 - DXGK_I2C_INTERFACE
---

# _DXGK_I2C_INTERFACE structure


## -description

The DXGK_I2C_INTERFACE structure contains pointers to functions in the <a href="/windows-hardware/drivers/ddi/index">I2C interface</a>, which is implemented by the display miniport driver.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The version number of the I2C interface. Version number constants are defined in <i>Dispmprt.h</i> (for example, DXGK_I2C_INTERFACE_VERSION_1).

### -field Context

A pointer to a private context block.

### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver.

### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver.

### -field DxgkDdiI2CTransmitDataToDisplay

A pointer to the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_i2c_transmit_data_to_display">DxgkDdiI2CTransmitDataToDisplay</a> function.

### -field DxgkDdiI2CReceiveDataFromDisplay

A pointer to the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_i2c_receive_data_from_display">DxgkDdiI2CReceiveDataFromDisplay</a> function.

## -remarks

A kernel-mode component that needs to use the I2C interface calls the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_interface">DxgkDdiQueryInterface</a> function.

