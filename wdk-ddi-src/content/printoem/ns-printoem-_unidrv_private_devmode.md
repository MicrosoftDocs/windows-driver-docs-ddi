---
UID: NS:printoem._UNIDRV_PRIVATE_DEVMODE
title: _UNIDRV_PRIVATE_DEVMODE (printoem.h)
description: The UNIDRV_PRIVATE_DEVMODE structure enables Unidrv plug-ins to determine the size of the private portion of Unidrv's DEVMODEW structure.
old-location: print\unidrv_private_devmode.htm
tech.root: print
ms.assetid: 91b8ba63-5276-43f8-81a6-07afc1a77ced
ms.date: 04/20/2018
keywords: ["_UNIDRV_PRIVATE_DEVMODE structure"]
ms.keywords: "*PUNIDRV_PRIVATE_DEVMODE, PUNIDRV_PRIVATE_DEVMODE, PUNIDRV_PRIVATE_DEVMODE structure pointer [Print Devices], UNIDRV_PRIVATE_DEVMODE, UNIDRV_PRIVATE_DEVMODE structure [Print Devices], _UNIDRV_PRIVATE_DEVMODE, print.unidrv_private_devmode, print_unidrv-pscript_ui_accecb33-b4e7-4e2d-a2f2-d792456eb9db.xml, printoem/PUNIDRV_PRIVATE_DEVMODE, printoem/UNIDRV_PRIVATE_DEVMODE"
f1_keywords:
 - "printoem/UNIDRV_PRIVATE_DEVMODE"
req.header: printoem.h
req.include-header: Printoem.h
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
- printoem.h
api_name:
- UNIDRV_PRIVATE_DEVMODE
product:
- Windows
targetos: Windows
req.typenames: UNIDRV_PRIVATE_DEVMODE, *PUNIDRV_PRIVATE_DEVMODE
---

# _UNIDRV_PRIVATE_DEVMODE structure

## -description

The UNIDRV_PRIVATE_DEVMODE structure enables Unidrv plug-ins to determine the size of the private portion of Unidrv's DEVMODEW structure.

## -struct-fields

### -field wReserved

Reserved for system use.

### -field wSize

The size, in bytes, of the private portion of Unidrv's [DEVMODEW](https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew) structure.

## -remarks

For information about the public and private sections of the DEVMODEW structure, see [The DEVMODEW Structure](https://docs.microsoft.com/windows-hardware/drivers/display/the-devmodew-structure).

Printoem.h defines a macro for determining the size of the private portion of Unidrv's DEVMODEW structure.

```cpp
#define GET_UNIDRV_PRIVATE_DEVMODE_SIZE(pdm)\
    ( ( (pdm)->dmDriverExtra > (FIELD_OFFSET(UNIDRV_PRIVATE_DEVMODE, wSize) + sizeof(WORD)) ) ? \
    ((PUNIDRV_PRIVATE_DEVMODE)((PBYTE)(pdm) + (pdm)-> dmSize)) -> wSize : 0 )
```

The pdm argument in the **GET_UNIDRV_PRIVATE_DEVMODE_SIZE** macro is a pointer to a DEVMODEW structure. The macro determines whether the value of the **dmDriverExtra** member of the DEVMODEW structure is larger than the byte offset of the **wSize** member of the UNIDRV_PRIVATE_DEVMODE structure. If so, the macro returns the value of the **wSize** member in the UNIDRV_PRIVATE_DEVMODE structure. If not, the macro returns zero.

To safely determine the address of the private portion of your plug-in's DEVMODEW structure, do the following:

1. Call the **GET_UNIDRV_PRIVATE_DEVMODE_SIZE** macro, passing the address of the DEVMODEW structure in the call.

2. Verify that (pdm)->dmDriverExtra is larger than the value returned by the macro. (The macro returns the value of the **wSize** member of the UNIDRV_PRIVATE_DEVMODE structure.)

3. Determine the address of the private portion of your plug-in's DEVMODEW structure as follows.

    ```cpp
    pdmPlugin = (PBYTE)(pdm) + (pdm)->dmSize + wSize;
    ```

    The preceding example starts with the address of the public DEVMODEW structure (pdm), adds the number of bytes of this structure (pdm->dmSize), and then adds the size in bytes of the Unidrv private DEVMODEW structure (**wSize**). A plug-in's private DEVMODEW data begins at this memory address. If there are multiple plug-ins chained together, the address returned by this example is that of the first plug-in's private DEVMODEW data. The second plug-in's private DEVMODEW data follows the first plug-in's private DEVMODEW data, the third plug-in's private DEVMODEW data follows that of the second plug-in's private DEVMODEW data, and so on. A plug-in developer who needs to determine the address of the *n*-th plug-in's private DEVMODEW data must know the sizes of the private DEVMODEW data for the first *n* - 1 plug-ins.

4. Verify that the private portion of your plug-in's DEVMODEW structure begins with a valid [OEM_DMEXTRAHEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oem_dmextraheader) structure.

## -see-also

[PSCRIPT5_PRIVATE_DEVMODE](https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_pscript5_private_devmode)
