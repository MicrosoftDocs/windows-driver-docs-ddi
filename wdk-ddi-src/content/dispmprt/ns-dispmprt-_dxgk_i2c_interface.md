---
UID: NS:dispmprt._DXGK_I2C_INTERFACE
title: "_DXGK_I2C_INTERFACE"
author: windows-driver-content
description: The DXGK_I2C_INTERFACE structure contains pointers to functions in the I2C interface, which is implemented by the display miniport driver.
old-location: display\dxgk_i2c_interface.htm
old-project: display
ms.assetid: aba0ebc8-2c92-4d27-a35b-9ac25ac6e5ab
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "_DXGK_I2C_INTERFACE, DXGK_I2C_INTERFACE structure [Display Devices], DXGK_I2C_INTERFACE, *PDXGK_I2C_INTERFACE, dispmprt/PDXGK_I2C_INTERFACE, PDXGK_I2C_INTERFACE, display.dxgk_i2c_interface, PDXGK_I2C_INTERFACE structure pointer [Display Devices], DmStructs_59985b59-bb86-459c-8bd2-2b6124a6b9bb.xml, dispmprt/DXGK_I2C_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DXGK_I2C_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_I2C_INTERFACE, *PDXGK_I2C_INTERFACE
---

# _DXGK_I2C_INTERFACE structure


## -description


The DXGK_I2C_INTERFACE structure contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567386">I2C interface</a>, which is implemented by the display miniport driver.


## -syntax


````
typedef struct _DXGK_I2C_INTERFACE {
  USHORT                                Size;
  USHORT                                Version;
  PVOID                                 Context;
  PINTERFACE_REFERENCE                  InterfaceReference;
  PINTERFACE_DEREFERENCE                InterfaceDereference;
  DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY  DxgkDdiI2CTransmitDataToDisplay;
  DXGKDDI_I2C_RECEIVE_DATA_FROM_DISPLAY DxgkDdiI2CReceiveDataFromDisplay;
} DXGK_I2C_INTERFACE, *PDXGK_I2C_INTERFACE;
````


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

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_i2c_transmit_data_to_display.md">DxgkDdiI2CTransmitDataToDisplay</a> function.


### -field DxgkDdiI2CReceiveDataFromDisplay

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_i2c_receive_data_from_display.md">DxgkDdiI2CReceiveDataFromDisplay</a> function.


## -remarks



A kernel-mode component that needs to use the I2C interface calls the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a> function.



