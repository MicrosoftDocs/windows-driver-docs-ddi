---
UID: NE:storport._SCSI_UNIT_CONTROL_TYPE
tech.root: storage
title: SCSI_UNIT_CONTROL_TYPE
ms.date: 05/24/2022
targetos: Windows
description: The SCSI_UNIT_CONTROL_TYPE enumeration contains unit control operations, where each control type initiates an action on a unit by the miniport driver. Storport specifies the control type when it calls a miniport's HwStorUnitControl routine.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _SCSI_UNIT_CONTROL_TYPE
 - PSCSI_UNIT_CONTROL_TYPE
 - SCSI_UNIT_CONTROL_TYPE
f1_keywords:
 - _SCSI_UNIT_CONTROL_TYPE
 - storport/_SCSI_UNIT_CONTROL_TYPE
 - PSCSI_UNIT_CONTROL_TYPE
 - storport/PSCSI_UNIT_CONTROL_TYPE
 - SCSI_UNIT_CONTROL_TYPE
 - storport/SCSI_UNIT_CONTROL_TYPE
dev_langs:
 - c++
---

## -description

The **SCSI_UNIT_CONTROL_TYPE** enumeration contains unit control operations, where each control type initiates an action on a unit by the miniport driver. Storport specifies the control type when it calls a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine.

## -enum-fields

### -field ScsiQuerySupportedUnitControlTypes

Reports the unit-control operations implemented by the miniport driver. A miniport must support this control type.

The Storport driver calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**SCSI_SUPPORTED_CONTROL_TYPE_LIST**](ns-storport-scsi_supported_control_type_list.md) structure after the HBA has been initialized but before the first I/O.

The miniport driver fills in the **SCSI_SUPPORTED_CONTROL_TYPE_LIST** structure with the operations that it supports. After **HwStorUnitControl** returns from this call, the Storport driver calls the miniport driver's **HwStorUnitControl** only for operations supported by the miniport.

### -field ScsiUnitUsage

Notifies the miniport whether the logical unit is used for any supported usage types. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_UC_DEVICE_USAGE**](ns-storport-stor_uc_device_usage.md) structure. Storport will call **HwStorUnitControl** separately for each usage type supported.

### -field ScsiUnitStart

Notifies the miniport to start a unit device. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to the [**STOR_ADDR_BTL8**](../scsi/ns-scsi-_stor_addr_btl8.md) address of the unit to start.

### -field ScsiUnitPower

Reports the unit power on or power off states. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_UNIT_CONTROL_POWER**](ns-storport-stor_unit_control_power.md) structure. If the miniport supports this control type, it will not receive a storage request block with SRB_FUNCTION_POWER.

### -field ScsiUnitPoFxPowerInfo

Notifies the miniport if idle power management is enabled or disabled on the unit component. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_POFX_UNIT_POWER_INFO**](ns-storport-stor_pofx_unit_power_info.md) structure. The miniport should call [**StorPortInitializePoFxPower**](nf-storport-storportinitializepofxpower.md) within this unit control if idle power management was enabled and if it supports runtime power management for the unit device.

### -field ScsiUnitPoFxPowerRequired

Notifies the miniport whether power is required for the unit component. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a[**STOR_POFX_POWER_REQUIRED_CONTEXT**](ns-storport-stor_pofx_power_required_context.md) structure.

### -field ScsiUnitPoFxPowerActive

Notifies the miniport that the unit component is either active or idle. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_POFX_ACTIVE_CONTEXT**](ns-storport-stor_pofx_active_context.md) structure.

### -field ScsiUnitPoFxPowerSetFState

Notifies the miniport to set the unit component to the given functional power state (F-state). Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_POFX_FSTATE_CONTEXT**](ns-storport-stor_pofx_fstate_context.md) structure. The miniport must support this control type if is specifies more than one F-state in the call to [**StorPortInitializePoFxPower**](nf-storport-storportinitializepofxpower.md).

### -field ScsiUnitPoFxPowerControl

Requests that the miniport execute a private power control operation that was initiated for the unit by a power engine plug-in (PEP). Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_POFX_POWER_CONTROL**](ns-storport-stor_pofx_power_control.md) structure.

### -field ScsiUnitRemove

Notifies the miniport that the unit has been removed. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to the [**STOR_ADDR_BTL8**](../scsi/ns-scsi-_stor_addr_btl8.md) address of the unit that was removed.

### -field ScsiUnitSurpriseRemoval

Notifies the miniport that the unit has been surprise-removed. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to the [**STOR_ADDR_BTL8**](../scsi/ns-scsi-_stor_addr_btl8.md) address of the unit that was surprise-removed.

### -field ScsiUnitRichDescription

The miniport can choose to support this if the device reports a longer vendor ID, model number, or firmware revision than is defined in the SCSI spec. Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_RICH_DEVICE_DESCRIPTION**](ns-storport-stor_rich_device_description.md) structure.

### -field ScsiUnitQueryBusType

Queries whether the miniport wants to specify a bus type for a given logical unit (LUN). Typically the bus type of a LUN and controller have the same bus type, but not always.  Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_UNIT_CONTROL_QUERY_BUS_TYPE**](ns-storport-stor_unit_control_query_bus_type.md) structure. Available in Windows 10 version 2004 and later.

> [!NOTE]
> In Windows 10 version 21H1 and later, Storport sends this control only if a miniport has also previously called [**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md) in its [**HwFindAdapter**](nc-storport-hw_find_adapter.md) routine with **StorportFeatureBusTypeUnitControl** specified.

### -field ScsiUnitQueryFruId

Queries the ID of a fault replacement unit (FRU). If the miniport supports this control type, Storport calls [**HwStorUnitControl**](nc-storport-hw_unit_control.md) with this control type and **Parameters** pointing to a [**STOR_FRU_ID_DESCRIPTION**](ns-storport-stor_fru_id_description.md) structure. Available in Windows 10 version 21H1 and later.

> [!NOTE]
> Storport sends this control only if a miniport has also previously called [**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md) in its [**HwFindAdapter**](nc-storport-hw_find_adapter.md) routine with **StorportFeatureFruIdUnitControl** specified.

### -field ScsiUnitReportInternalData

Reserved for system use. Available starting in Windows 11, version 22H2.

### -field ScsiUnitControlMax

Maximum control type value.

### -field MakeUnitControlTypeSizeOfUlong

Makes this enumeration the size of a ULONG.

## -remarks

A miniport reports which control types it supports when Storport calls the miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine with a control type of **ScsiQuerySupportedControlTypes**. For those control types that the miniport supports, Storport calls **HwStorUnitControl** with a **SCSI_UNIT_CONTROL_TYPE** value that specifies the unit control operation to be performed by the miniport.

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)
