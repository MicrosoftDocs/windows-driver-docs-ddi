---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS
title: IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS (ehstorioctl.h)
description: This IOCTL returns a result set containing the enumeration of all active storage Physical Device Objects (PDOs) associated with the given Addressable Command Target (ACT).
old-location: storage\ioctl_ehstor_device_enumerate_pdos.htm
tech.root: storage
ms.assetid: 900A8CAB-287D-4D92-B4CB-2959E87C8E67
ms.date: 03/29/2018
keywords: ["IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS IOCTL"]
ms.keywords: IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS, IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS control, IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS, storage.ioctl_ehstor_device_enumerate_pdos
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
req.typenames: 
f1_keywords:
 - IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS
 - ehstorioctl/IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorIoctl.h
api_name:
 - IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS
---

# IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS IOCTL


## -description

This IOCTL returns a result set containing the enumeration of all active storage Physical Device Objects (PDOs) associated with the given Addressable Command Target (ACT). The client may first probe for the required buffer size by issuing this IOCTL in the following manner:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DeviceIoControl(
    hDevice,
    IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS,
    &pdoType,
    sizeof(PDO_TYPE),
    NULL,
    0,
    &dwBytesRequired,
    NULL );</pre>
</td>
</tr>
</table></span></div>
With the output buffer parameter set to <b>NULL</b>, the I/O manager clears the IRP_INPUT_OPERATION bit in the IRP flags. Upon detecting this, the storage silo driver can safely set IoStatus.Information to the required buffer size, thus indicating it to the client.

This only works because STATUS_BUFFER_OVERFLOW (0x80000005) is an NT_WARNING() value for which I/O manager copies IoStatus.Information into the lpBytesReturned parameter, returning that value to the client.

Caution is required here because IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS is defined with METHOD_BUFFERED, therefore I/O manager will attempt to copy this number of bytes into the output buffer.

## -ioctlparameters

### -input-buffer

The input buffer at Irp->AssociatedIrp.SystemBuffer must contain a ULONG value as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ne-ehstorioctl-_pdo_type">PDO_TYPE</a>,

where either all of the PDOs, just the disk PDO, just the control PDO or all silo PDOs are enumerated respectively according to the provided PDO_TYPE input value.

### -input-buffer-length

The length of a ULONG.

### -output-buffer

Irp->AssociatedIrp.SystemBuffer points to the buffer that will receive the PDO enumeration results. If the client supplied a non-<b>NULL</b> buffer with the issued IOCTL, then the driver fills it with the result set only if the Parameters.DeviceIoControl.The return value is STATUS_SUCCESS if the buffer size is sufficient and the results have been copied to the buffer. Otherwise STATUS_INVALID_BUFFER_SIZE is returned and the output buffer is unmodified.

The returned enumeration buffer contains a result set structured according to the following rules. The leading structure in the buffer, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ns-ehstorioctl-_enum_pdo_results">ENUM_PDO_RESULTS</a>, consists of a structure count and an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ns-ehstorioctl-_enum_pdo_entry">ENUM_PDO_ENTRY</a> structures.

### -output-buffer-length

OutputBufferLength indicates a buffer size of sufficient length to include the entire result set.

### -in-out-buffer

### -inout-buffer-length

### -status-block

One of the following values may be returned in the Status field:


<dl>
<dd>
STATUS_SUCCESS - The output buffer contains the enumeration of the requested PDOs.

</dd>
</dl>



<dl>
<dd>
STATUS_BUFFER_OVERFLOW - The Information field is set to the required buffer size to contain the entire enumeration result set output.

</dd>
</dl>



<dl>
<dd>
STATUS_INVALID_BUFFER_SIZE - The output buffer length supplied is insufficient to contain the entire enumeration result set output.

</dd>
</dl>

