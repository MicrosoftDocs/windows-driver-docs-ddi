---
UID: NS:dispmprt._DXGK_FIRMWARE_TABLE_INTERFACE
title: _DXGK_FIRMWARE_TABLE_INTERFACE (dispmprt.h)
description: Contains functions that user-mode display drivers can use to read and enumerate the system firmware table. These functions are supplied by the Microsoft DirectX graphics kernel subsystem and can be called by WDDM 1.2 and later user-mode display drivers.
old-location: display\dxgk_firmware_table_interface.htm
tech.root: display
ms.assetid: 22ba50eb-e428-433f-aca0-1d61f31fcd0c
ms.date: 05/10/2018
keywords: ["_DXGK_FIRMWARE_TABLE_INTERFACE structure"]
ms.keywords: "'ACPI', 'FIRM', 'RSMB', *PDXGK_FIRMWARE_TABLE_INTERFACE, DXGK_FIRMWARE_TABLE_INTERFACE, DXGK_FIRMWARE_TABLE_INTERFACE structure [Display Devices], PDXGK_FIRMWARE_TABLE_INTERFACE, PDXGK_FIRMWARE_TABLE_INTERFACE structure pointer [Display Devices], _DXGK_FIRMWARE_TABLE_INTERFACE, display.dxgk_firmware_table_interface, dispmprt/DXGK_FIRMWARE_TABLE_INTERFACE, dispmprt/PDXGK_FIRMWARE_TABLE_INTERFACE"
f1_keywords:
 - "dispmprt/DXGK_FIRMWARE_TABLE_INTERFACE"
 - "DXGK_FIRMWARE_TABLE_INTERFACE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- DXGK_FIRMWARE_TABLE_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: DXGK_FIRMWARE_TABLE_INTERFACE, *PDXGK_FIRMWARE_TABLE_INTERFACE
---

# _DXGK_FIRMWARE_TABLE_INTERFACE structure


## -description


Contains functions that user-mode display drivers can use to read and enumerate the system firmware table. These functions are supplied by the Microsoft DirectX graphics kernel subsystem and can be called by WDDM 1.2 and later user-mode display drivers.




## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The version number of the System Firmware Table interface. Version number constants are defined in Dispmprt.h (for example, <b>DXGK_FIRMWARE_TABLE_INTERFACE_VERSION_1</b>).


### -field Context

A pointer to a context that is provided by the display port driver.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display port driver.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display port driver.


### -field EnumSystemFirmwareTables

Enumerates the system firmware table. All input parameters are supplied by the display miniport driver.

Syntax:

```cpp
NTSTATUS EnumSystemFirmwareTables(
  _In_      VOID  *Context,
  _In_      ULONG ProviderSignature,
  _In_      ULONG TableId,
  _In_      ULONG BufferSize,
  _Out_opt_ VOID  *Buffer,
  _Out_     ULONG *RequiredSize
);
```

The raw SMBIOS table provider ('RSMB') currently returns a single table identifier, 0x0000. This corresponds to the raw SMBIOS firmware table.



The raw firmware table provider ('FIRM') returns a list of <b>DWORD</b> table identifiers. Each identifier corresponds to the beginning of a physical address range. Currently, this provider returns 'C0000' and 'E0000'. These values correspond to physical memory from 0xC0000 to 0xDFFFF and 0xE0000 to 0xFFFFF, respectively.



The ACPI table provider ('ACPI') returns a list of <b>DWORD</b> table identifiers. Each identifier returned corresponds to the <b>Signature</b> member of the <b>DESCRIPTION_HEADER</b> structure for an ACPI table currently in the ACPI namespace of the system.



For ACPI, if the system contains multiple tables with the same name, they are all enumerated with EnumSystemFirmwareTables. However, ReadSystemFirmwareTable retrieves only the first table in the list with this name.



#### Context

A handle to a context block that is associated with a display adapter. The display miniport driver's DxgkDdiAddDevice function previously provided this handle to the DirectX graphics kernel subsystem.





#### ProviderSignature

The identifier of the firmware table provider to which the query is to be directed. This parameter can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| **'ACPI'** | The ACPI firmware table provider. | 
| **'FIRM'** | The raw firmware table provider. | 
| **'RSMB'** | The raw SMBIOS firmware table provider. |


#### TableId

The identifier of the firmware table. This identifier is in little-endian format, so you must reverse the characters in the string. 

For example, FACP is an ACPI provider, as described in the <b>Signature</b> member of the <b>DESCRIPTION_HEADER</b> structure in the [ACPI specification](https://uefi.org/specifications). Therefore, use 'PCAF' to specify the FACP table, as shown in the following example:

```cpp
retVal = ReadSystemFirmwareTable('ACPI', 'PCAF', pBuffer, BUFSIZE);
```


#### BufferSize

The size of the buffer pointed to by the <i>Buffer</i> parameter, in bytes.



#### Buffer

An optional pointer to a buffer that receives the list of firmware tables. If this parameter is <b>NULL</b>, the return value is the required buffer size.

For more information on the contents of this buffer, see the Remarks section.



#### RequiredSize

A pointer to a value that receives the minimum size of the  buffer pointed to by <i>Buffer</i>, in bytes, that the operating system needs to process the enumeration request.


### -field ReadSystemFirmwareTable

Reads the system firmware table. All input parameters are supplied by the display miniport driver.

```cpp
NTSTATUS ReadSystemFirmwareTable(
  _In_      VOID  *Context,
  _In_      ULONG ProviderSignature,
  _In_      ULONG TableId,
  _In_      ULONG BufferSize,
  _Out_opt_ VOID  *Buffer,
  _Out_     ULONG *RequiredSize
);
```


The raw SMBIOS table provider ('RSMB') retrieves the contents of the raw SMBIOS firmware table. The buffer pointed to by the <i>Buffer</i> parameter receives the following data:

```cpp
#include <windows.h>

struct RawSMBIOSData
{
    BYTE    Used20CallingMethod;
    BYTE    SMBIOSMajorVersion;
    BYTE    SMBIOSMinorVersion;
    BYTE    DmiRevision;
    DWORD    Length;
    BYTE    SMBIOSTableData[];
};
```

The raw firmware table provider ('FIRM') retrieves the contents of the specified physical address range. ReadSystemFirmwareTable returns the size of the address range.

The ACPI table provider ('ACPI') retrieves the contents of the specified ACPI table. Because OEMs can include ACPI firmware tables that are not listed in the ACPI specification, you should first call the EnumSystemFirmwareTables function to enumerate all ACPI tables that are currently on the system.

For ACPI, if the system contains multiple tables with the same name, they are all enumerated with EnumSystemFirmwareTables. However, ReadSystemFirmwareTable retrieves only the first table in the list with this name.



#### Context

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.



#### ProviderSignature

The identifier of the firmware table provider to which the query is to be directed. This parameter can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| **'ACPI'** | The ACPI firmware table provider. | 
| **'FIRM'** | The raw firmware table provider. | 
| **'RSMB'** | The raw SMBIOS firmware table provider. | 


#### TableId

The identifier of the firmware table. This identifier is in little-endian format, so you must reverse the characters in the string. 

For example, FACP is an ACPI provider, as described in the <b>Signature</b> member of the <b>DESCRIPTION_HEADER</b> structure in the [ACPI specification](https://uefi.org/specifications). Therefore, use 'PCAF' to specify the FACP table, as shown in the following example:

```cpp
retVal = ReadSystemFirmwareTable('ACPI', 'PCAF', pBuffer, BUFSIZE);
```


#### BufferSize

The size of the buffer pointed to by the <i>Buffer</i> parameter, in bytes.



#### Buffer

An optional pointer to a buffer that receives the requested firmware table. If this parameter is <b>NULL</b>, the return value is the required buffer size.

For more information on the contents of this buffer, see the Remarks section.



#### RequiredSize

A pointer to a value that receives the minimum size of the  buffer pointed to by <i>Buffer</i>, in bytes, that the operating system needs to process the read request.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_firmware_table_interface">EnumSystemFirmwareTables</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_firmware_table_interface">ReadSystemFirmwareTable</a>
 

 

