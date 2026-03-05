---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE
title: EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE (iddcx.h)
description: EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE is called by the OS to return data received from an I2C device in a monitor.
prerelease: true
tech.root: display
ms.date: 02/17/2026
keywords: ["EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE callback function"]
ms.keywords: EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE, EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE callback, EvtIddCxMonitorI2cTransmitAndReceive, EvtIddCxMonitorI2cTransmitAndReceive callback function [Display Devices], PFN_IDD_CX_MONITOR_I2C_TRANSMIT, PFN_IDD_CX_MONITOR_I2C_TRANSMIT callback function pointer [Display Devices], display.evt_idd_cx_monitor_i2c_transmit, iddcx/EvtIddCxMonitorI2cTransmit
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
req.irql: _requires_same_
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE
 - iddcx/EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE
---

# EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE callback function

## -description

**EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE** is called by the OS to return data received from an I2C device in a monitor.

## -parameters

### -param MonitorObject [in]

The OS context handle for this monitor returned by the [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md) call.

### -param pInArgs [in]

Input arguments of the function.

### -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

### -remarks

IddCx 1.11 drivers that support I2C must supply this DDI as well as the existing [**EVT_IDD_CX_MONITOR_I2C_TRANSMIT**](nc-iddcx-evt_idd_cx_monitor_i2c_transmit.md) and [**EVT_IDD_CX_MONITOR_I2C_RECEIVE**](nc-iddcx-evt_idd_cx_monitor_i2c_receive.md).

The new **EVT_IDD_CX_MONITOR_I2C_TRANSMIT_AND_RECEIVE** DDI allows a driver to complete an I2C operation in the context of one call as opposed to the old DDIs where the driver would have to hold on to the received data until the OS called **EVT_IDD_CX_MONITOR_I2C_RECEIVE**.

> [!NOTE]
> It's possible an OS that supports IddCx 1.11 doesn't support this functionality. In this case, it's safe for the driver to expose the new function, but the OS doesn't use it.

> [!NOTE]
> IddCx 1.11 drivers that support I2C must also expose the existing **EVT_IDD_CX_MONITOR_I2C_TRANSMIT** and EVT_IDD_CX_MONITOR_I2C_RECEIVE DDs.

## -see-also

[**IDARG_IN_I2C_TRANSMIT_AND_RECEIVE**](ns-iddcx-idarg_in_i2c_transmit_and_receive.md)

[IddCx versions](/windows-hardware/drivers/display/iddcx-versions)