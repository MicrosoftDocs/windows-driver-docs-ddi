---
UID: NC:dot11wificxintf.MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE
tech.root: netvista
title: MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE (dot11wificxintf.h)
ms.date: 10/02/2021
ms.topic: language-reference
targetos: Windows
description: The MiniportWdiAdapterHangDiagnose function is used to collect hardware control register states and optionally full firmware state.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxintf.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - dot11wificxintf.h
api_name:
 - MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE
f1_keywords:
 - MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE
 - dot11wificxintf/MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE
dev_langs:
 - c++
---


## -description

The *MiniportWdiAdapterHangDiagnose* handler function is used to collect hardware control register states and optionally full firmware state.

This is a WDI miniport handler inside [**NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS**](ns-dot11wificxintf-ndis_miniport_driver_wdi_characteristics.md).

> [!NOTE] You must declare the function by using the **MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE** type.

## -parameters

### -param MiniportDriverContext 

[in]
The handle to a driver-allocated context area where the driver maintains state and configuration information. The miniport driver passed this context area to the [*NdisMRegisterWdiMiniportDriver*](nf-dot11wificxintf-ndismregisterwdiminiportdriver.md) function.

### -param DiagnoseLevel 

[in]
The diagnose level, as defined in the [**eDiagnoseLevel**](ne-dot11wificxintf-ediagnoselevel.md) enumeration. The default level is **DiagnoseLevelHardwareRegisters**, 1KB maximum in the output buffer.

### -param BufferSize 

[in]
The size of **FirmwareBlob**, in bytes.

### -param FirmwareBlob 

[out]
A pointer to the buffer that will contain the hardware control registry states, and optionally full firmware state.

### -param pOutputSize 

[out]
A pointer to the number of bytes written to **FirmwareBlob**.

## -returns

The return value is ignored.

## -remarks

The default diagnose level is **DiagnoseLevelHardwareRegisters**, with 1KB maximum in the output buffer.

## -see-also

<a href="/windows-hardware/drivers/network/wdi-hang-detection-and-recovery">WDI hang detection and recovery</a>

[**NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS**](ns-dot11wificxintf-ndis_miniport_driver_wdi_characteristics.md)

[**eDiagnoseLevel**](ne-dot11wificxintf-ediagnoselevel.md)

[*NdisMRegisterWdiMiniportDriver*](nf-dot11wificxintf-ndismregisterwdiminiportdriver.md)

