---
UID: NS:dispmprt._DXGK_FIRMWARE_TABLE_INTERFACE
title: "_DXGK_FIRMWARE_TABLE_INTERFACE"
author: windows-driver-content
description: Contains functions that user-mode display drivers can use to read and enumerate the system firmware table. These functions are supplied by the Microsoft DirectX graphics kernel subsystem and can be called by WDDM 1.2 and later user-mode display drivers.
old-location: display\dxgk_firmware_table_interface.htm
old-project: display
ms.assetid: 22ba50eb-e428-433f-aca0-1d61f31fcd0c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "'ACPI', 'FIRM', 'RSMB', *PDXGK_FIRMWARE_TABLE_INTERFACE, DXGK_FIRMWARE_TABLE_INTERFACE, DXGK_FIRMWARE_TABLE_INTERFACE structure [Display Devices], PDXGK_FIRMWARE_TABLE_INTERFACE, PDXGK_FIRMWARE_TABLE_INTERFACE structure pointer [Display Devices], _DXGK_FIRMWARE_TABLE_INTERFACE, display.dxgk_firmware_table_interface, dispmprt/DXGK_FIRMWARE_TABLE_INTERFACE, dispmprt/PDXGK_FIRMWARE_TABLE_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_FIRMWARE_TABLE_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_FIRMWARE_TABLE_INTERFACE, *PDXGK_FIRMWARE_TABLE_INTERFACE
---

# _DXGK_FIRMWARE_TABLE_INTERFACE structure


## -description


Contains functions that user-mode display drivers can use to read and enumerate the system firmware table. These functions are supplied by the Microsoft DirectX graphics kernel subsystem and can be called by WDDM 1.2 and later user-mode display drivers.




## -syntax


````
typedef struct _DXGK_FIRMWARE_TABLE_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  NTSTATUS               (*EnumSystemFirmwareTables)(
      _In_ VOID *Context, 
      _In_ ULONG ProviderSignature, 
      _In_ ULONG TableId, 
      _In_ ULONG BufferSize, 
      _Out_opt_ VOID *Buffer, 
      _Out_ ULONG *RequiredSize);
  NTSTATUS               (*ReadSystemFirmwareTable)(
      _In_ VOID *Context, 
      _In_ ULONG ProviderSignature, 
      _In_ ULONG TableId, 
      _In_ ULONG BufferSize, 
      _Out_opt_ VOID *Buffer, 
      _Out_ ULONG *RequiredSize);
} DXGK_FIRMWARE_TABLE_INTERFACE, *PDXGK_FIRMWARE_TABLE_INTERFACE;
````


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


<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>NTSTATUS EnumSystemFirmwareTables(
  _In_      VOID  *Context,
  _In_      ULONG ProviderSignature,
  _In_      ULONG TableId,
  _In_      ULONG BufferSize,
  _Out_opt_ VOID  *Buffer,
  _Out_     ULONG *RequiredSize
);
</pre>
</td>
</tr>
</table></span></div>


The raw SMBIOS table provider ('RSMB') currently returns a single table identifier, 0x0000. This corresponds to the raw SMBIOS firmware table.



The raw firmware table provider ('FIRM') returns a list of <b>DWORD</b> table identifiers. Each identifier corresponds to the beginning of a physical address range. Currently, this provider returns 'C0000' and 'E0000'. These values correspond to physical memory from 0xC0000 to 0xDFFFF and 0xE0000 to 0xFFFFF, respectively.



The ACPI table provider ('ACPI') returns a list of <b>DWORD</b> table identifiers. Each identifier returned corresponds to the <b>Signature</b> member of the <b>DESCRIPTION_HEADER</b> structure for an ACPI table currently in the ACPI namespace of the system.



For ACPI, if the system contains multiple tables with the same name, they are all enumerated with EnumSystemFirmwareTables. However, ReadSystemFirmwareTable retrieves only the first table in the list with this name.



#### Context

A handle to a context block that is associated with a display adapter. The display miniport driver's DxgkDdiAddDevice function previously provided this handle to the DirectX graphics kernel subsystem.





#### ProviderSignature

The identifier of the firmware table provider to which the query is to be directed. This parameter can be one of the following values.





<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="_ACPI_"></a><a id="_acpi_"></a><dl>
<dt><b>'ACPI'</b></dt>
</dl>
</td>
<td width="60%">
The ACPI firmware table provider.

</td>
</tr>
<tr>
<td width="40%"><a id="_FIRM_"></a><a id="_firm_"></a><dl>
<dt><b>'FIRM'</b></dt>
</dl>
</td>
<td width="60%">
The raw firmware table provider.

</td>
</tr>
<tr>
<td width="40%"><a id="_RSMB_"></a><a id="_rsmb_"></a><dl>
<dt><b>'RSMB'</b></dt>
</dl>
</td>
<td width="60%">
The raw SMBIOS firmware table provider.

</td>
</tr>
</table>
 



#### TableId

The identifier of the firmware table. This identifier is in little-endian format, so you must reverse the characters in the string. 

For example, FACP is an ACPI provider, as described in the <b>Signature</b> member of the <b>DESCRIPTION_HEADER</b> structure in the ACPI specification (see http://www.acpi.info). Therefore, use 'PCAF' to specify the FACP table, as shown in the following example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>retVal = ReadSystemFirmwareTable('ACPI', 'PCAF', pBuffer, BUFSIZE);</pre>
</td>
</tr>
</table></span></div>


#### BufferSize

The size of the buffer pointed to by the <i>Buffer</i> parameter, in bytes.



#### Buffer

An optional pointer to a buffer that receives the list of firmware tables. If this parameter is <b>NULL</b>, the return value is the required buffer size.

For more information on the contents of this buffer, see the Remarks section.



#### RequiredSize

A pointer to a value that receives the minimum size of the  buffer pointed to by <i>Buffer</i>, in bytes, that the operating system needs to process the enumeration request.


### -field ReadSystemFirmwareTable

Reads the system firmware table. All input parameters are supplied by the display miniport driver.


<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>NTSTATUS ReadSystemFirmwareTable(
  _In_      VOID  *Context,
  _In_      ULONG ProviderSignature,
  _In_      ULONG TableId,
  _In_      ULONG BufferSize,
  _Out_opt_ VOID  *Buffer,
  _Out_     ULONG *RequiredSize
);
</pre>
</td>
</tr>
</table></span></div>


The raw SMBIOS table provider ('RSMB') retrieves the contents of the raw SMBIOS firmware table. The buffer pointed to by the <i>Buffer</i> parameter receives the following data:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#include &lt;windows.h&gt;

struct RawSMBIOSData
{
    BYTE    Used20CallingMethod;
    BYTE    SMBIOSMajorVersion;
    BYTE    SMBIOSMinorVersion;
    BYTE    DmiRevision;
    DWORD    Length;
    BYTE    SMBIOSTableData[];
};
</pre>
</td>
</tr>
</table></span></div>
The raw firmware table provider ('FIRM') retrieves the contents of the specified physical address range. ReadSystemFirmwareTable returns the size of the address range.

The ACPI table provider ('ACPI') retrieves the contents of the specified ACPI table. Because OEMs can include ACPI firmware tables that are not listed in the ACPI specification, you should first call the EnumSystemFirmwareTables function to enumerate all ACPI tables that are currently on the system.

For ACPI, if the system contains multiple tables with the same name, they are all enumerated with EnumSystemFirmwareTables. However, ReadSystemFirmwareTable retrieves only the first table in the list with this name.



#### Context

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.



#### ProviderSignature

The identifier of the firmware table provider to which the query is to be directed. This parameter can be one of the following values.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="_ACPI_"></a><a id="_acpi_"></a><dl>
<dt><b>'ACPI'</b></dt>
</dl>
</td>
<td width="60%">
The ACPI firmware table provider.

</td>
</tr>
<tr>
<td width="40%"><a id="_FIRM_"></a><a id="_firm_"></a><dl>
<dt><b>'FIRM'</b></dt>
</dl>
</td>
<td width="60%">
The raw firmware table provider.

</td>
</tr>
<tr>
<td width="40%"><a id="_RSMB_"></a><a id="_rsmb_"></a><dl>
<dt><b>'RSMB'</b></dt>
</dl>
</td>
<td width="60%">
The raw SMBIOS firmware table provider.

</td>
</tr>
</table>
 



#### TableId

The identifier of the firmware table. This identifier is in little-endian format, so you must reverse the characters in the string. 

For example, FACP is an ACPI provider, as described in the <b>Signature</b> member of the <b>DESCRIPTION_HEADER</b> structure in the ACPI specification (see http://www.acpi.info). Therefore, use 'PCAF' to specify the FACP table, as shown in the following example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>retVal = ReadSystemFirmwareTable('ACPI', 'PCAF', pBuffer, BUFSIZE);</pre>
</td>
</tr>
</table></span></div>


#### BufferSize

The size of the buffer pointed to by the <i>Buffer</i> parameter, in bytes.



#### Buffer

An optional pointer to a buffer that receives the requested firmware table. If this parameter is <b>NULL</b>, the return value is the required buffer size.

For more information on the contents of this buffer, see the Remarks section.



#### RequiredSize

A pointer to a value that receives the minimum size of the  buffer pointed to by <i>Buffer</i>, in bytes, that the operating system needs to process the read request.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh802471">ReadSystemFirmwareTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh802466">EnumSystemFirmwareTables</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_FIRMWARE_TABLE_INTERFACE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

