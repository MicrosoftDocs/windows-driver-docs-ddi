---
UID: NE:storport._STOR_DEVICE_POWER_STATE
tech.root: storage
title: STOR_DEVICE_POWER_STATE (storport.h)
ms.date: 05/13/2021
ms.topic: language-reference
description: The STOR_DEVICE_POWER_STATE enumerator specifies a storage device power state.
keywords: ["STOR_DEVICE_POWER_STATE enumeration"]
ms.keywords: "*PSTOR_DEVICE_POWER_STATE, PSTOR_DEVICE_POWER_STATE, PSTOR_DEVICE_POWER_STATE enumeration pointer [Storage Devices], STOR_DEVICE_POWER_STATE, STOR_DEVICE_POWER_STATE enumeration [Storage Devices], StorPowerDeviceD0, StorPowerDeviceD1, StorPowerDeviceD2, StorPowerDeviceD3, StorPowerDeviceMaximum, StorPowerDeviceUnspecified, _STOR_DEVICE_POWER_STATE, storage.stor_device_power_state, storport/PSTOR_DEVICE_POWER_STATE, storport/STOR_DEVICE_POWER_STATE, storport/StorPowerDeviceD0, storport/StorPowerDeviceD1, storport/StorPowerDeviceD2, storport/StorPowerDeviceD3, storport/StorPowerDeviceMaximum, storport/StorPowerDeviceUnspecified, structs-storport_1b3e3040-821f-4cc1-9a5b-15ae5eaeb35e.xml"
req.construct-type: enumeration
req.header: storport.h
req.include-header: Storport.h, Minitape.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
f1_keywords:
 - _STOR_DEVICE_POWER_STATE
 - storport/_STOR_DEVICE_POWER_STATE
 - PSTOR_DEVICE_POWER_STATE
 - storport/PSTOR_DEVICE_POWER_STATE
 - STOR_DEVICE_POWER_STATE
 - storport/STOR_DEVICE_POWER_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_DEVICE_POWER_STATE
 - PSTOR_DEVICE_POWER_STATE
 - STOR_DEVICE_POWER_STATE
---

# STOR_DEVICE_POWER_STATE enumeration (storport.h)

## -description

The **STOR_DEVICE_POWER_STATE** enumerator specifies a storage device power state.

## -enum-fields

### -field StorPowerDeviceUnspecified

The device power state is unspecified.

### -field StorPowerDeviceD0

Maximum device power state, which corresponds to [device working state D0](/windows-hardware/drivers/kernel/device-working-state-d0).

### -field StorPowerDeviceD1

The [device sleeping state](/windows-hardware/drivers/kernel/device-sleeping-states) that is less than **StorPowerDeviceD0** and greater than **StorPowerDeviceD2**, which corresponds to device power state D1.

### -field StorPowerDeviceD2

The device sleeping state that is less than **StorPowerDeviceD1** and greater than **StorPowerDeviceD3**, which corresponds to device power state D2.

### -field StorPowerDeviceD3

The lowest-powered device sleeping state, which corresponds to device power state D3.

### -field StorPowerDeviceMaximum

The upper delimiting value on device power states.

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**SCSI_POWER_REQUEST_BLOCK**](ns-storport-_scsi_power_request_block.md)

[**STOR_UNIT_CONTROL_POWER**](ns-storport-stor_unit_control_power.md)
