---
UID: NS:gpioclx._CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
title: _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT (gpioclx.h)
description: The CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure contains information about the power-management capabilities of a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\client_query_bank_power_information_output.htm
tech.root: GPIO
ms.date: 08/02/2022
keywords: ["CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure"]
ms.keywords: "*PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure [Parallel Ports], GPIO.client_query_bank_power_information_output, PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure pointer [Parallel Ports], _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, gpioclx/CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, gpioclx/PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT"
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.typenames: CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, *PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
f1_keywords:
 - _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
 - gpioclx/_CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
 - PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
 - gpioclx/PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
 - CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
 - gpioclx/CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Gpioclx.h
api_name:
 - _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
 - PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
 - CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
---

# _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure

## -description

The **CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT** structure contains information about the power-management capabilities of a bank of general-purpose I/O (GPIO) pins.

## -struct-fields

### -field F1StateSupported

Indicates whether the GPIO bank supports [component-level power management](/windows-hardware/drivers/kernel/component-level-power-management). If this flag is set, the GPIO bank supports component-level power management. Otherwise, it does not. A GPIO bank that supports power management can change between the F0 (fully powered) state and the F1 (low-power) state independently of the Fx power states of the other banks in the GPIO controller. A GPIO bank that does not support component-level power management is always in the F0 power state when the controller is in the D0 power state.

### -field Reserved

Not used.

### -field F1IdleStateParameters

A **PO_FX_COMPONENT_IDLE_STATE** structure that describes the parameters (transition latency, residency requirement, and so on) for the F1 power state of the GPIO bank. For more information about these parameters, see [PO_FX_COMPONENT_IDLE_STATE](/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_idle_state).

## -remarks

The unnamed struct inside _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT contains a set of power-management flag bits.

The **BankPowerInformation** member of the [CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT](/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_query_set_information_output) structure is a structure of type **CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT**.

For more information about GPIO banks, see [Partioning a GPIO Controller into Banks of Pins](/windows-hardware/drivers/gpio/partitioning-a-gpio-controller-into-banks-of-pins).

## -see-also

- [CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT](/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_query_set_information_output)
- [PO_FX_COMPONENT_IDLE_STATE](/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_idle_state)
