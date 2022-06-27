---
UID: NS:minitape._STOR_DEVICE_CAPABILITIES_EX
title: STOR_DEVICE_CAPABILITIES_EX (minitape.h)
description: The _STOR_DEVICE_CAPABILITIES_EX structure (minitape.h) contains extended device capabilities information relevant to storage devices.
old-location: storage\stor_device_capabilities_ex.htm
tech.root: storage
ms.date: 05/20/2022
keywords: ["STOR_DEVICE_CAPABILITIES_EX structure"]
ms.keywords: "*PSTOR_DEVICE_CAPABILITIES_EX, PSTOR_DEVICE_CAPABILITIES_EX, PSTOR_DEVICE_CAPABILITIES_EX structure pointer [Storage Devices], STOR_DEVICE_CAPABILITIES_EX, STOR_DEVICE_CAPABILITIES_EX structure [Storage Devices], _STOR_DEVICE_CAPABILITIES_EX, storage.stor_device_capabilities_ex, storport/PSTOR_DEVICE_CAPABILITIES_EX, storport/STOR_DEVICE_CAPABILITIES_EX"
req.header: minitape.h
req.include-header: Storport.h, Minitape.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: STOR_DEVICE_CAPABILITIES_EX, *PSTOR_DEVICE_CAPABILITIES_EX
f1_keywords:
 - _STOR_DEVICE_CAPABILITIES_EX
 - minitape/_STOR_DEVICE_CAPABILITIES_EX
 - PSTOR_DEVICE_CAPABILITIES_EX
 - minitape/PSTOR_DEVICE_CAPABILITIES_EX
 - STOR_DEVICE_CAPABILITIES_EX
 - minitape/STOR_DEVICE_CAPABILITIES_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_DEVICE_CAPABILITIES_EX
 - PSTOR_DEVICE_CAPABILITIES_EX
 - STOR_DEVICE_CAPABILITIES_EX
---

# STOR_DEVICE_CAPABILITIES_EX structure (minitape.h)

## -description

The **STOR_DEVICE_CAPABILITIES_EX** structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP. **STOR_DEVICE_CAPABILITIES** is a subset of the [**DEVICE_CAPABILITIES**](../wdm/ns-wdm-_device_capabilities.md) structure containing the members relevant to storage devices.

## -struct-fields

### -field Version

Specifies the version of the structure. Storport sets this field to STOR_DEVICE_CAPABILITIES_EX_VERSION_1.

### -field Size

Specifies the size of the structure. Storport sets this field to ```sizeof(STOR_DEVICE_CAPABILITIES_EX)```.

### -field DeviceD1

Specifies whether the device hardware supports the D1 power state. Miniport drivers set this bit to 0.

### -field DeviceD2

Specifies whether the device hardware supports the D2 power state. Miniport drivers set this bit to 0.

### -field LockSupported

Specifies whether the device supports physical-device locking that prevents device ejection. This member pertains to ejecting a LUN or a unit device.

### -field EjectSupported

Specifies whether the device supports software-controlled device ejection while the system is in the **PowerSystemWorking** state. This member pertains to ejecting a LUN or unit device.

### -field Removable

Specifies whether the device can be dynamically removed from its immediate parent. If **Removable** is set to **TRUE**, the device does not belong to the same physical object as its parent.

If **Removable** is set to **TRUE**, the device is displayed in the Unplug or Eject Hardware program, unless **SurpriseRemovalOK** is also set to **TRUE**.

### -field DockDevice

Specifies whether the device is a docking peripheral.

### -field UniqueID

Specifies whether the device's instance ID is unique system-wide. This bit is clear if the instance ID is unique only within the scope of the bus.

### -field SilentInstall

Specifies whether **Device Manager** should suppress all installation dialog boxes; except required dialog boxes such as "no compatible drivers found."

### -field RawDeviceOK

Specifies whether the driver for the underlying bus can drive the device if there is no function driver (for example, SCSI devices in pass-through mode). This mode of operation is called raw mode.

### -field SurpriseRemovalOK

Specifies whether the miniport driver for the device can handle the case where the device is removed before Storport can send SRB_FUNCTION_PNP with **StorRemoveDevice** as the **PnPAction** in the [**SCSI_PNP_REQUEST_BLOCK**](../storport/ns-storport-_scsi_pnp_request_block.md) structure. If **SurpriseRemovalOK** is set to **TRUE**, the device can be safely removed from its immediate parent regardless of the state that its driver is in.

### -field NoDisplayInUI

Do not display the device in the user interface. If this bit is set, the device is never displayed in the user interface, even if the device is present but fails to start. Miniport drivers do not set this bit.

### -field DefaultWriteCacheEnabled

The storage device's write cache is enabled by default at initialization.

### -field Reserved0

Reserved bits.

### -field Address

LUN address of the storage unit device.

### -field UINumber

Specifies a number associated with the device that can be displayed in the user interface.

This number might be an ID value chosen to make locating the physical device easier for the user. When the **UINumber** is unknown, the miniport driver can set this member to its default value of 0xFFFFFFFF.

### -field Reserved1

Reserved bits.

## -remarks

When a miniport driver receives an SRB in its [**HwStorStartIo**](../storport/nc-storport-hw_startio.md) routine where the SRB function is SRB_FUNCTION_PNP, the SRB is formatted as a [**SCSI_PNP_REQUEST_BLOCK**](../storport/ns-storport-_scsi_pnp_request_block.md) structure. If the **PnPAction** member of the SRB is **StorQueryCapabilities**, the miniport can return a **STOR_DEVICE_CAPABILITIES_EX** structure in the **DataBuffer** member of the SRB.

The eject, removal, and install characteristics for the device are set in the **STOR_DEVICE_CAPABILITIES_EX** structure. To support the use of this structure, the miniport must set the  STOR_FEATURE_FULL_PNP_DEVICE_CAPABILITIES flag in the  **FeatureSupport** flags member in [**HW_INITIALIZATION_DATA**](../storport/ns-storport-_hw_initialization_data-r1.md) before calling [**StorPortInitialize**](../storport/nf-storport-storportinitialize.md).

## -see-also

[**DEVICE_CAPABILITIES**](../wdm/ns-wdm-_device_capabilities.md)

[**HW_INITIALIZATION_DATA**](../storport/ns-storport-_hw_initialization_data-r1.md)
[**SCSI_PNP_REQUEST_BLOCK**](../storport/ns-storport-_scsi_pnp_request_block.md)

[**StorPortInitialize**](../storport/nf-storport-storportinitialize.md)
