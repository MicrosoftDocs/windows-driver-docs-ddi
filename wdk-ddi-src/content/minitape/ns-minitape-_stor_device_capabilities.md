---
UID: NS:minitape._STOR_DEVICE_CAPABILITIES
title: STOR_DEVICE_CAPABILITIES (minitape.h)
description: The _STOR_DEVICE_CAPABILITIES structure (minitape.h) contains device capabilities information relevant to storage devices.
old-location: storage\stor_device_capabilities.htm
tech.root: storage
ms.date: 05/20/2022
keywords: ["STOR_DEVICE_CAPABILITIES structure"]
ms.keywords: "*PSTOR_DEVICE_CAPABILITIES, PSTOR_DEVICE_CAPABILITIES, PSTOR_DEVICE_CAPABILITIES structure pointer [Storage Devices], STOR_DEVICE_CAPABILITIES, STOR_DEVICE_CAPABILITIES structure [Storage Devices], _STOR_DEVICE_CAPABILITIES, storage.stor_device_capabilities, storport/PSTOR_DEVICE_CAPABILITIES, storport/STOR_DEVICE_CAPABILITIES"
req.header: minitape.h
req.include-header: Storport.h, Minitape.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.typenames: STOR_DEVICE_CAPABILITIES, *PSTOR_DEVICE_CAPABILITIES
f1_keywords:
 - _STOR_DEVICE_CAPABILITIES
 - minitape/_STOR_DEVICE_CAPABILITIES
 - PSTOR_DEVICE_CAPABILITIES
 - minitape/PSTOR_DEVICE_CAPABILITIES
 - STOR_DEVICE_CAPABILITIES
 - minitape/STOR_DEVICE_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_DEVICE_CAPABILITIES
 - PSTOR_DEVICE_CAPABILITIES
 - STOR_DEVICE_CAPABILITIES
---

# STOR_DEVICE_CAPABILITIES structure (minitape.h)

## -description

The **STOR_DEVICE_CAPABILITIES** structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP. **STOR_DEVICE_CAPABILITIES** is a subset of the [**DEVICE_CAPABILITIES**](../wdm/ns-wdm-_device_capabilities.md) structure containing the members relevant to storage devices.

## -struct-fields

### -field Version

Specifies the version of the structure. Storport sets this field to STOR_DEVICE_CAPABILITIES_EX_VERSION_1.

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

### -field SurpriseRemovalOK

Specifies whether the miniport driver for the device can handle the case where the device is removed before Storport can send SRB_FUNCTION_PNP with **StorRemoveDevice** as the **PnPAction** in the [**SCSI_PNP_REQUEST_BLOCK**](../storport/ns-storport-_scsi_pnp_request_block.md) structure. If **SurpriseRemovalOK** is set to **TRUE**, the device can be safely removed from its immediate parent regardless of the state that its driver is in.

### -field NoDisplayInUI

Do not display the device in the user interface. If this bit is set, the device is never displayed in the user interface, even if the device is present but fails to start. Miniport drivers do not set this bit.

## -remarks

When a miniport driver receives an SRB in its [**HwStorStartIo**](../storport/nc-storport-hw_startio.md) routine where the SRB function is SRB_FUNCTION_PNP, the SRB is formatted as a [**SCSI_PNP_REQUEST_BLOCK**](../storport/ns-storport-_scsi_pnp_request_block.md) structure. If the **PnPAction** member of the SRB is **StorQueryCapabilities**, the miniport can return a **STOR_DEVICE_CAPABILITIES** structure in the **DataBuffer** member of the SRB.

Storport sends this structure to the miniport with all members initialized to 0. On return, only the **Removable** field is used from this structure.

Starting with Windows 8, miniports should use the [**STOR_DEVICE_CAPABILITIES_EX**](../storport/ns-storport-_stor_device_capabilities_ex.md) structure to indicate support for additional capabilities.

## -see-also

[**DEVICE_CAPABILITIES**](../wdm/ns-wdm-_device_capabilities.md)

[**SCSI_PNP_REQUEST_BLOCK**](../storport/ns-storport-_scsi_pnp_request_block.md)

[**STOR_DEVICE_CAPABILITIES_EX**](../storport/ns-storport-_stor_device_capabilities_ex.md)
