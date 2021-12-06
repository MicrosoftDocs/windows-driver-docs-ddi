---
UID: NC:srb.PHW_FIND_ADAPTER
title: PHW_FIND_ADAPTER (srb.h)
description: The PHW_FIND_ADAPTER prototype declares a routine that uses supplied configuration to determine whether a specific HBA is supported and, if it is, to return configuration information about that adapter.
old-location: storage\phw_find_adapter.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["PHW_FIND_ADAPTER callback"]
ms.keywords: "(*PHW_FIND_ADAPTER), (*PHW_FIND_ADAPTER) callback function [Storage Devices], ide_minikr_dcd06c33-80a8-417c-acf6-5c38fa4d62ed.xml, srb/(*PHW_FIND_ADAPTER), storage.phw_find_adapter"
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
f1_keywords:
 - PHW_FIND_ADAPTER
 - srb/PHW_FIND_ADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - srb.h
api_name:
 - PHW_FIND_ADAPTER
---

# PHW_FIND_ADAPTER callback

## -description

The PHW_FIND_ADAPTER prototype declares a routine that uses supplied configuration to determine whether a specific HBA is supported and, if it is, to return configuration information about that adapter.

## -parameters

### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.

### -param HwContext [in]

Reserved member when used by one of the Storport driver's miniport drivers. With SCSI miniport drivers this member points to a context value. For a description of the meaning of this member for a SCSI miniport driver, see [**HwScsiFindAdapter**](/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)).

### -param BusInformation [in]

Reserved member when used by one of the Storport driver's miniport drivers. With SCSI miniport drivers this member points to bus-type-specific information that the OS-specific port driver has gathered. For a complete description of the meaning of this member for a SCSI miniport driver, see [**HwScsiFindAdapter**](/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)).

### -param ArgumentString [in]

Reserved member when used by one of the Storport driver's miniport drivers. With SCSI miniport drivers this member points to a null-terminated ASCII string that contains device information such as a base parameter or an interrupt level from the registry. For a complete description of the meaning of this member for a SCSI miniport driver, see [**HwScsiFindAdapter**](/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)).

### -param ConfigInfo [in, out]

Pointer to a [**PORT_CONFIGURATION_INFORMATION**](ns-srb-_port_configuration_information.md) structure that contains configuration information for the HBA.

### -param Again [out]

Reserved member when used by one of the Storport driver's miniport drivers. With SCSI miniport drivers this member points to a BOOLEAN variable that informs the port driver whether it should call this routine again. For more information about the meaning of this member for a SCSI miniport driver, see [**HwScsiFindAdapter**](/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)).

## -returns

The routine declared by this prototype must return one of the following status values:

| Return code | Description |
| ----------- | ----------- |
| SP_RETURN_FOUND      | Indicates a supported HBA was found and that the HBA-relevant configuration information was successfully determined and set in the PORT_CONFIGURATION_INFORMATION structure. |
| SP_RETURN_ERROR      | Indicates an HBA was found but there was error obtaining the configuration information. If possible, such an error should be logged with [**ScsiPortLogError**](nf-srb-scsiportlogerror.md). |
| SP_RETURN_BAD_CONFIG | Indicates the supplied configuration information was invalid for the adapter. |
| SP_RETURN_NOT_FOUND  | Indicates no supported HBA was found for the supplied configuration information. |

## -remarks

This declaration is used by both SCSI and StorPort miniport drivers.

For more information about the SCSI miniport driver's version of the routine associated with this declaration, see [**HwScsiFindAdapter**](/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)).

For more information about the Storport driver's version of the routine associated with this declaration, see [**HwStorFindAdapter**](../storport/nc-storport-hw_find_adapter.md).

## -see-also

[**HwScsiFindAdapter**](/previous-versions/windows/hardware/drivers/ff557300(v=vs.85))

[**HwStorFindAdapter**](../storport/nc-storport-hw_find_adapter.md)
