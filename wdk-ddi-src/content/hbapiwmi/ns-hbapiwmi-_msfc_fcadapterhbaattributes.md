---
UID: NS:hbapiwmi._MSFC_FCAdapterHBAAttributes
title: _MSFC_FCAdapterHBAAttributes (hbapiwmi.h)
description: The MSFC_FCAdapterHBAAttributes structure is used by a WMI provider to expose attribute information associated with a fibre channel adapter.
old-location: storage\msfc_fcadapterhbaattributes.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MSFC_FCAdapterHBAAttributes structure"]
ms.keywords: "*PMSFC_FCAdapterHBAAttributes, MSFC_FCAdapterHBAAttributes, MSFC_FCAdapterHBAAttributes structure [Storage Devices], PMSFC_FCAdapterHBAAttributes, PMSFC_FCAdapterHBAAttributes structure pointer [Storage Devices], _MSFC_FCAdapterHBAAttributes, hbapiwmi/MSFC_FCAdapterHBAAttributes, hbapiwmi/PMSFC_FCAdapterHBAAttributes, storage.msfc_fcadapterhbaattributes, structs-Fibre_07d902b9-2da0-4bca-94ab-db837beff481.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
targetos: Windows
req.typenames: MSFC_FCAdapterHBAAttributes, *PMSFC_FCAdapterHBAAttributes
f1_keywords:
 - _MSFC_FCAdapterHBAAttributes
 - hbapiwmi/_MSFC_FCAdapterHBAAttributes
 - PMSFC_FCAdapterHBAAttributes
 - hbapiwmi/PMSFC_FCAdapterHBAAttributes
 - MSFC_FCAdapterHBAAttributes
 - hbapiwmi/MSFC_FCAdapterHBAAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - MSFC_FCAdapterHBAAttributes
---

# _MSFC_FCAdapterHBAAttributes structure


## -description

The MSFC_FCAdapterHBAAttributes structure is used by a WMI provider to expose attribute information associated with a fibre channel adapter.

## -struct-fields

### -field UniqueAdapterId

Indicates the unique adapter ID.

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field NodeWWN

Contains the 64 bit world-wide name that indicates the node name of the HBA. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

### -field VendorSpecificID

Indicates a vendor-specific ID.

### -field NumberOfPorts

Indicates the number of ports on the HBA.

### -field Manufacturer

Contains an ASCII string that is 64 bytes or fewer in length and that identifies the name of the manufacturer of the HBA.

### -field SerialNumber

Contains an ASCII string that is 64 bytes or fewer in length and that identifies the serial number of the HBA.

### -field Model

Contains an ASCII string that is 256 bytes or fewer in length and that identifies the vendor-specific name of the HBA model.

### -field ModelDescription

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the model description.

### -field NodeSymbolicName

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the symbolic name for the fibre channel node.

### -field HardwareVersion

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific hardware revision level of the HBA.

### -field DriverVersion

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific version of the HBA miniport driver.

### -field OptionROMVersion

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific option ROM or BIOS version of the HBA.

### -field FirmwareVersion

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific firmware version of the HBA.

### -field DriverName

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the file name for the driver binary file.

### -field MfgDomain

Contains the name of the HBA manufacturer.

## -see-also

<a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>



<a href="/windows-hardware/drivers/storage/msfc-fcadapterhbaattributes-wmi-class">MSFC_FCAdapterHBAAttributes WMI Class</a>
