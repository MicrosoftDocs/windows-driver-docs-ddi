---
UID: NS:dispmprt._DXGK_DP_INTERFACE
title: DXGK_DP_INTERFACE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: A kernel-mode component that needs to use the DXGK_DP_INTERFACE DisplayPort (DP) interface calls the display miniport driver's DxgkDdiQueryInterface function.
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DP_INTERFACE, *PDXGK_DP_INTERFACE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DP_INTERFACE
 - DXGK_DP_INTERFACE
f1_keywords:
 - _DXGK_DP_INTERFACE
 - dispmprt/_DXGK_DP_INTERFACE
 - PDXGK_DP_INTERFACE
 - dispmprt/PDXGK_DP_INTERFACE
 - DXGK_DP_INTERFACE
 - dispmprt/DXGK_DP_INTERFACE
dev_langs:
 - c++
---

# DXGK_DP_INTERFACE structure


## -description

A kernel-mode component that needs to use the DXGK_DP_INTERFACE DisplayPort (DP) interface calls the display miniport driver's [DxgkDdiQueryInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_interface) function.

## -struct-fields

### -field Size

Size, in bytes, of this structure.

### -field Version

Version number of the DP interface. Version numbers constants are defined in *dispmprt.h* (for example, DXGK_DP_INTERFACE_VERSION_1).

### -field Context

Pointer to a private context block provided by the display miniport driver.

### -field InterfaceReference

[**PINTERFACE_REFERENCE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference) interface reference function that is implemented by the display miniport driver.

### -field InterfaceDereference

[**PINTERFACE_DEREFERENCE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference) interface dereference function that is implemented by the display miniport driver.

### -field DsiQueryCaps

Pointer to the display miniport driver's [DXGKDDI_QUERYDPCAPS](nc-dispmprt-dxgkddi_querydpcaps.md) function.

### -field DxgkDdiGetDPAddress

Pointer to the display miniport driver's [DXGKDDI_GETDPADDRESS](nc-dispmprt-dxgkddi_getdpaddress.md) function.

### -field DxgkDdiDPAuxIoTransmission

Pointer to the display miniport driver's [DXGKDDI_DPAUXIOTRANSMISSION](nc-dispmprt-dxgkddi_dpauxiotransmission.md) function.

### -field DxgkDdiDPI2CIoTransmission

Pointer to the display miniport driver's [DXGKDDI_DPI2CIOTRANSMISSION](nc-dispmprt-dxgkddi_dpi2ciotransmission.md) function.

### -field DxgkDdiDPSBMTransmission

Pointer to the display miniport driver's [DXGKDDI_DPSBMTRANSMISSION](nc-dispmprt-dxgkddi_dpsbmtransmission.md) function.

## -remarks

|Minimum supported client|Header|IRQL|
|:----------------------:|:----:|:--:|
|Available in WDDM 2.7 and later version|dispmprt.h(include Dispmprt.h)|PASSIVE_LEVEL|

## -see-also

[DXGKDDI_DPAUXIOTRANSMISSION](nc-dispmprt-dxgkddi_dpauxiotransmission.md)

[DXGKDDI_DPI2CIOTRANSMISSION](nc-dispmprt-dxgkddi_dpi2ciotransmission.md)

[DXGKDDI_DPSBMTRANSMISSION](nc-dispmprt-dxgkddi_dpsbmtransmission.md)

[DXGKDDI_GETDPADDRESS](nc-dispmprt-dxgkddi_getdpaddress.md)

[DXGKDDI_QUERYDPCAPS](nc-dispmprt-dxgkddi_querydpcaps.md)

[**PINTERFACE_DEREFERENCE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference)

[**PINTERFACE_REFERENCE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference)

