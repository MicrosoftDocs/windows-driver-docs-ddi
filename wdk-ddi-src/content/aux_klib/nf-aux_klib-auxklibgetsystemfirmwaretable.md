---
UID: NF:aux_klib.AuxKlibGetSystemFirmwareTable
title: AuxKlibGetSystemFirmwareTable function
author: windows-driver-content
description: The AuxKlibGetSystemFirmwareTable routine retrieves the specified firmware table from the firmware table provider.
old-location: kernel\auxklibgetsystemfirmwaretable.htm
old-project: kernel
ms.assetid: 548C850F-87AF-43E0-BD87-5531D9874D4D
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, AuxKlibGetSystemFirmwareTable, AuxKlibGetSystemFirmwareTable routine [Kernel-Mode Driver Architecture], F, G, K, S, T, a, aux_klib/AuxKlibGetSystemFirmwareTable, b, e, i, kernel.auxklibgetsystemfirmwaretable, l, m, r, s, t, u, w, x, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows Vista.
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
req.lib: Aux_Klib.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Aux_Klib.lib
-	Aux_Klib.dll
apiname:
-	AuxKlibGetSystemFirmwareTable
product: Windows
targetos: Windows
req.typenames: REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA
---

# AuxKlibGetSystemFirmwareTable function


## -description


The <b>AuxKlibGetSystemFirmwareTable</b> routine retrieves the specified firmware table from the firmware table provider.


## -syntax


````
NTSTATUS AuxKlibGetSystemFirmwareTable(
  _In_      ULONG  FirmwareTableProviderSignature,
  _In_      ULONG  FirmwareTableID,
  _Out_opt_ PVOID  FirmwareTableBuffer,
  _In_      ULONG  BufferLength,
  _Out_opt_ PULONG ReturnLength
);
````


## -parameters




### -param FirmwareTableProviderSignature [in]

The identifier of the firmware table provider to which the query is to be directed. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
'ACPI'

</td>
<td>
The ACPI firmware table provider.

</td>
</tr>
<tr>
<td>
'FIRM'

</td>
<td>
The raw firmware table provider.

</td>
</tr>
<tr>
<td>
'RSMB'

</td>
<td>
The raw SMBIOS firmware table provider.

</td>
</tr>
</table>
 


### -param FirmwareTableID [in]

The identifier of the firmware table. The characters in the identifier are in little-endian order.

For example, FACP is the name of a table provided by ACPI. The FACP table is identified by the 4-byte value 'PCAF' (0x50434146) in the <b>Signature</b> field of the <b>DESCRIPTION_HEADER</b> structure at the start of the table. The following code example shows how to specify FACP in an <b>AuxKlibGetSystemFirmwareTable</b> call:

<code>status = AuxKlibGetSystemFirmwareTable('ACPI', 'PCAF', pBuffer, BUFSIZE, &amp;dataSize);</code>

In this example, <code>pBuffer</code> points to the caller-allocated buffer, <code>BUFSIZE</code> is the size in bytes of this buffer, and <code>dataSize</code> is a variable to which the routine writes the number of bytes written to the buffer. For more information about the <b>DESCRIPTION_HEADER</b> structure, see the Advanced Configuration and Power Interface Specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=57185">Advanced Configuration and Power Interface</a> website.


### -param FirmwareTableBuffer [out, optional]

A pointer to a caller-allocated buffer that receives the list of firmware tables. If this parameter is NULL, the value written to *<i>ReturnLength</i> is the required buffer size. For more information about the contents of this buffer, see the Remarks section.


### -param BufferLength [in]

The size, in bytes, of the buffer pointed to by <i>FirmwareTableBuffer</i>.


### -param ReturnLength [out, optional]

A pointer to a location to which the routine writes the number of bytes of data written to the buffer pointed to by <i>FirmwareTableBuffer</i>.


## -returns



<b>AuxKlibGetSystemFirmwareTable</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied to the routine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The caller-allocated buffer is too small, but the required buffer size has been written to the <i>ReturnLength</i> output parameter.

</td>
</tr>
</table>
 




## -remarks



The raw SMBIOS table provider ('RSMB') retrieves the contents of the raw SMBIOS firmware table. The data written to the <i>FirmwareTableBuffer</i> buffer starts with the following structure:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct RawSMBIOSData
{
  BYTE  Used20CallingMethod;
  BYTE  SMBIOSMajorVersion;
  BYTE  SMBIOSMinorVersion;
  BYTE  DmiRevision;
  DWORD  Length;
  BYTE  SMBIOSTableData[];
};</pre>
</td>
</tr>
</table></span></div>
The raw firmware table provider ('FIRM') retrieves the contents of the specified physical address range. The value written to *<i>ReturnLength</i> is the size of the address range.

The ACPI table provider ('ACPI') retrieves the contents of the specified ACPI table. Because OEMs can include ACPI firmware tables that are not listed in the ACPI specification, you should first call <a href="..\aux_klib\nf-aux_klib-auxklibenumeratesystemfirmwaretables.md">AuxKlibEnumerateSystemFirmwareTables</a> to enumerate all ACPI tables that are currently available from the system firmware.

For ACPI, if the system firmware contains multiple tables with the same name, <b>AuxKlibEnumerateSystemFirmwareTables</b> enumerates them all. However, <b>AuxKlibGetSystemFirmwareTable</b> retrieves only the first table in the list that has this name.

<b>AuxKlibGetSystemFirmwareTable</b> is the kernel-mode equivalent of the Win32 <a href="https://msdn.microsoft.com/3bfe81ca-6d04-4da1-9579-6b0b48faa4a2">GetSystemFirmwareTable</a> function.

Drivers must call <a href="..\aux_klib\nf-aux_klib-auxklibinitialize.md">AuxKlibInitialize</a> before calling <b>AuxKlibGetSystemFirmwareTable</b>.

<b>AuxKlibGetSystemFirmwareTable</b> is defined in the Aux_klib.h header file that is included in the WDK for Windows 8 and later versions of Windows. To use this routine, drivers should link to the version of Aux_klib.lib that is included in the WDK for Windows 8 and later versions of Windows. The implementation of <b>AuxKlibGetSystemFirmwareTable</b> in these versions of the WDK can be used in versions of Windows starting with Windows Vista.




## -see-also

<a href="..\aux_klib\nf-aux_klib-auxklibenumeratesystemfirmwaretables.md">AuxKlibEnumerateSystemFirmwareTables</a>



<a href="..\aux_klib\nf-aux_klib-auxklibinitialize.md">AuxKlibInitialize</a>



<a href="https://msdn.microsoft.com/3bfe81ca-6d04-4da1-9579-6b0b48faa4a2">GetSystemFirmwareTable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AuxKlibGetSystemFirmwareTable routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

