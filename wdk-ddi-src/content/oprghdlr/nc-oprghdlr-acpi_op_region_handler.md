---
UID: NC:oprghdlr.ACPI_OP_REGION_HANDLER
title: ACPI_OP_REGION_HANDLER (oprghdlr.h)
description: An ACPI_OP_REGION_HANDLER-typed routine is supplied by an ACPI device function driver to provide access by the ACPI driver to the device's operation region.
old-location: acpi\pacpi_op_region_handler.htm
tech.root: acpi
ms.assetid: c3a5af59-c97c-42be-bc43-afa30ad710ec
ms.date: 02/15/2018
keywords: ["ACPI_OP_REGION_HANDLER callback function"]
ms.keywords: ACPI_OP_REGION_HANDLER, ACPI_OP_REGION_HANDLER callback, AcpiOpRegionHandler, AcpiOpRegionHandler callback function [ACPI Devices], acpi.pacpi_op_region_handler, opregref_be7bf2cd-0369-4efd-bbdb-5ad7dc28c33d.xml, oprghdlr/AcpiOpRegionHandler
f1_keywords:
 - "oprghdlr/AcpiOpRegionHandler"
req.header: oprghdlr.h
req.include-header: Oprghdlr.h
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
req.irql: (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- oprghdlr.h
api_name:
- AcpiOpRegionHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# ACPI_OP_REGION_HANDLER callback function


## -description


An ACPI_OP_REGION_HANDLER-typed routine is supplied by an ACPI device function driver to provide access by the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/acpi-driver">ACPI driver</a> to the device's operation region.


## -parameters




### -param AccessType

Specifies one of the following access types.

<table>
<tr>
<th>Access Type</th>
<th>Description</th>
</tr>
<tr>
<td>
ACPI_OPREGION_WRITE 

</td>
<td>
Write to the operation region memory buffer.

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_READ

</td>
<td>
Read from the operation region memory buffer.

</td>
</tr>
</table>
 


### -param OperationRegionObject

Specifies the operation region object returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nf-oprghdlr-registeropregionhandler">RegisterOpRegionHandler</a> for the operation region handler.


### -param Address

Specifies a byte offset in the operation region memory buffer. Depending on the access type, data is transferred to or from this memory location. 


### -param Size

Specifies the number of bytes to access.


### -param Data

Pointer to the data buffer supplied by the ACPI driver that is associated with the access. For a read access, bytes are transferred from the operation region memory buffer to the data buffer. For a write access, bytes are transferred from the data buffer to the operation region memory buffer.


### -param Context

Pointer to the same operation region context that the function driver specified when it registered the operation region handler.


### -param CompletionHandler

Reserved for internal use.


### -param CompletionContext

Reserved for internal use.


## -returns



Returns one of the following status values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The access was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The access type is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_Xxx</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred.

</td>
</tr>
</table>
 




## -remarks



When the ACPI driver calls an operation region handler, it specifies values for <i>Address</i> and <i>Size</i> that ensure that the access is within the operation region that is defined in the ACPI BIOS for the ACPI device. The ACPI device function driver must ensure that the operation region memory buffer it allocates is at least as large, in bytes, as the operation region defined for the ACPI device.

For more information about operation region handlers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/supporting-an-operation-region">Supporting an Operation Region</a>.

An ACPI_OP_REGION_HANDLER-typed routine runs at the caller's IRQL.

For detailed information about constraints on operation regions, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=57185">Advanced Configuration and Power Interface (ACPI) Specification</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nf-oprghdlr-deregisteropregionhandler">DeRegisterOpRegionHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nf-oprghdlr-registeropregionhandler">RegisterOpRegionHandler</a>
 

 

