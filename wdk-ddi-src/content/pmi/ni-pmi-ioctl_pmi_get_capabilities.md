---
UID: NI:pmi.IOCTL_PMI_GET_CAPABILITIES
title: IOCTL_PMI_GET_CAPABILITIES (pmi.h)
description: The IOCTL_PMI_GET_CAPABILITIES request obtains the capability and asset information about a power meter.
old-location: powermeter\ioctl_pmi_get_capabilities.htm
tech.root: powermeter
ms.assetid: 2b8fb604-944d-40fc-be5b-a287ca7e3ea1
ms.date: 05/08/2018
keywords: ["IOCTL_PMI_GET_CAPABILITIES IOCTL"]
ms.keywords: IOCTL_PMI_GET_CAPABILITIES, IOCTL_PMI_GET_CAPABILITIES control, IOCTL_PMI_GET_CAPABILITIES control code [Power Metering and Budgeting Devices], PowerMeterRef_4328d6ef-f85e-4375-9505-ff9134969d60.xml, pmi/IOCTL_PMI_GET_CAPABILITIES, powermeter.ioctl_pmi_get_capabilities
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
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
 - IOCTL_PMI_GET_CAPABILITIES
 - pmi/IOCTL_PMI_GET_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pmi.h
api_name:
 - IOCTL_PMI_GET_CAPABILITIES
---

# IOCTL_PMI_GET_CAPABILITIES IOCTL


## -description

The <b>IOCTL_PMI_GET_CAPABILITIES</b> request obtains the capability and asset information about a power meter.

## -ioctlparameters

### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member of the I/O request packet (IRP) points to an initiator-allocated buffer that is used both as the input buffer and the output buffer for the request. On input, this buffer contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a> structure in which the <b>Version</b> and <b>CapabilityType</b> members are set to valid values. The <b>CapabilitiesType</b> member contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_capabilities_type">PMI_CAPABILITIES_TYPE</a> enumeration value that specifies the type of PMI capability information to be retrieved from the power meter. This value also determines the size of the output buffer required to contain this information.

### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IRP's current I/O stack location (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>) is set to the size in bytes of the buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member. This size must be greater than or equal to <b>sizeof</b>(<b>PMI_CAPABILITIES</b>) or the request will fail with an error status of STATUS_INVALID_PARAMETER.

### -output-buffer

If the request completes successfully, the buffer pointed to by the <b>AssociatedIrp.SystemBuffer</b> member contains the requested PMI capability information. Located at the start of this buffer is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a> structure that indicates the type and size of the information in the buffer.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the IRP's current I/O stack location is set to the size in bytes of the buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member. For the request to succeed, this size must be large enough to contain the PMI capability information specified by the <b>PMI_CAPABILITIES_TYPE</b> input parameter value. Otherwise, the request will fail with error status STATUS_BUFFER_TOO_SMALL.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a> structure and its variable-length data.

The <b>Status</b> member is set to one of the following values:




**STATUS_BUFFER_TOO_SMALL**

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> is less than the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a> structure and its variable-length data. 


**STATUS_INVALID_PARAMETER**

The initiator-allocated input buffer contains an invalid <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_capabilities_type">PMI_CAPABILITIES_TYPE</a> value.


**STATUS_SUCCESS**

The WDM driver that supports the PMI interface has completed the IOCTL request successfully.

## -remarks

The <b>IOCTL_PMI_GET_CAPABILITIES</b> request queries the PMI capabilities or asset information of the power meter. The input <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a> enumeration value specifies the type of capability information to be returned. The data type and contents of the output buffer vary based on the data requested.

The following table describes the type of data that is returned for the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_capabilities_type">PMI_CAPABILITIES_TYPE</a> enumeration value.

<table>
<tr>
<th>PMI_CAPABILITIES_TYPE value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>PmiMeteredHardware</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_metered_hardware_information">PMI_METERED_HARDWARE_INFORMATION</a> structure that specifies the hardware devices that the power meter monitors. 

</td>
</tr>
<tr>
<td>
<b>PmiReportedCapabilities</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a> structure that specifies the types of PMI capabilities the power meter supports.

<div class="alert"><b>Note</b>  The <b>PMI_REPORTED_CAPABILITIES</b> structure is variable-length. The driver must fail this IOCTL request if the output buffer (referenced by the <b>MdlAddress</b> member of the IRP) is too small.</div>
<div> </div>
</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_capabilities_type">PMI_CAPABILITIES_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_metered_hardware_information">PMI_METERED_HARDWARE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>

