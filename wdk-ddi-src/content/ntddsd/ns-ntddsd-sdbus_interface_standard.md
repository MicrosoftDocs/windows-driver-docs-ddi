---
UID: NS:ntddsd._SDBUS_INTERFACE_STANDARD
tech.root: sd
title: SDBUS_INTERFACE_STANDARD
ms.date: 10/06/2022
targetos: Windows
description: Learn more about the SDBUS_INTERFACE_STANDARD structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddsd.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: SDBUS_INTERFACE_STANDARD, *PSDBUS_INTERFACE_STANDARD
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddsd.h
api_name:
 - _SDBUS_INTERFACE_STANDARD
 - PSDBUS_INTERFACE_STANDARD
 - SDBUS_INTERFACE_STANDARD
f1_keywords:
 - _SDBUS_INTERFACE_STANDARD
 - ntddsd/_SDBUS_INTERFACE_STANDARD
 - PSDBUS_INTERFACE_STANDARD
 - ntddsd/PSDBUS_INTERFACE_STANDARD
 - SDBUS_INTERFACE_STANDARD
 - ntddsd/SDBUS_INTERFACE_STANDARD
dev_langs:
 - c++
helpviewer_keywords:
 - _SDBUS_INTERFACE_STANDARD
---

## -description

The SDBUS\_INTERFACE\_STANDARD structure contains pointers to the method routines of a Secure Digital (SD) card bus interface.

## -struct-fields

### -field Size

Indicates the size, in bytes, of this structure. The caller of [**SdBusOpenInterface**](nf-ntddsd-sdbusopeninterface.md) should set this member to **sizeof**(SDBUS\_INTERFACE\_STANDARD).

### -field Version

Indicates the version number of the interface. The caller of **SdBusOpenInterface** should set this member to SDBUS\_INTERFACE\_VERSION.

### -field Context

Pointer to context information that the bus driver provides whenever a device driver opens an interface with **SdBusOpenInterface**. This information is available to the caller on output after the call to **SdBusOpenInterface**. The caller must pass this information as a parameter to other interface routines.

### -field InterfaceReference

Pointer to a bus driver-supplied routine of type PINTERFACE\_REFERENCE that increments the interface's reference count that is available to the caller of the **SdBusOpenInterface** routine when this routine returns. **SdBusOpenInterface** automatically increments the interface count to one, so in most cases, it is necessary for the caller to use this routine.

This routine follows the standard format of bus interface reference routines. For a description of the general case, see [**INTERFACE**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface).

### -field InterfaceDereference

Pointer to a bus driver-supplied routine of type PINTERFACE\_DEREFERENCE that decrements the interface reference count. If the caller decrements the reference count to zero, the bus driver closes the interface.

This routine follows the standard format of bus interface dereference routines. For a description of the general case, see [**INTERFACE**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface).

Device drivers must use this routine to dereference the interface under the following conditions:

- The device driver receives a query remove IRP.
- The device driver receives a surprise remove IRP.
- The device driver receives a remove IRP, without first receiving a query remove or a surprise remove IRP.

In all of these cases, the device driver should dereference the interface before passing the IRP to the bus driver.

### -field InitializeInterface

Pointer to a bus driver-supplied routine of type [**PSDBUS\_INITIALIZE\_INTERFACE\_ROUTINE**](nc-ntddsd-psdbus_initialize_interface_routine.md) that sets initialization parameters on the interface.

### -field AcknowledgeInterrupt

Pointer to a bus driver-supplied routine of type [**PSDBUS\_ACKNOWLEDGE\_INT\_ROUTINE**](nc-ntddsd-psdbus_acknowledge_int_routine.md) that the SD device driver uses to notify the bus driver that it has finished processing an interrupt.

## -remarks

SD device drivers must obtain this set of method routines to communicate with the SD bus driver. Drivers call the [**SdBusOpenInterface**](nf-ntddsd-sdbusopeninterface.md) library routine to open an interface.

## -see-also

[**INTERFACE**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface)

[**PSDBUS\_ACKNOWLEDGE\_INT\_ROUTINE**](nc-ntddsd-psdbus_acknowledge_int_routine.md)

[**SDBUS\_INTERFACE\_STANDARD**](ns-ntddsd-sdbus_interface_standard.md)

[**SdBusOpenInterface**](nf-ntddsd-sdbusopeninterface.md)
