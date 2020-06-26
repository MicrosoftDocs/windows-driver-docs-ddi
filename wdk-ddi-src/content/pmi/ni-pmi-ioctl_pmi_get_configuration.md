---
UID: NI:pmi.IOCTL_PMI_GET_CONFIGURATION
title: IOCTL_PMI_GET_CONFIGURATION (pmi.h)
description: The IOCTL_PMI_GET_CONFIGURATION request returns information about the current configuration of a power meter.
old-location: powermeter\ioctl_pmi_get_configuration.htm
tech.root: powermeter
ms.assetid: 957a2658-dddc-4529-8697-5fa44fcb96c2
ms.date: 05/08/2018
keywords: ["IOCTL_PMI_GET_CONFIGURATION IOCTL"]
ms.keywords: IOCTL_PMI_GET_CONFIGURATION, IOCTL_PMI_GET_CONFIGURATION control, IOCTL_PMI_GET_CONFIGURATION control code [Power Metering and Budgeting Devices], PowerMeterRef_7d1f1fbc-cd7a-4885-8d41-8f42c4659de7.xml, pmi/IOCTL_PMI_GET_CONFIGURATION, powermeter.ioctl_pmi_get_configuration
f1_keywords:
 - "pmi/IOCTL_PMI_GET_CONFIGURATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pmi.h
api_name:
- IOCTL_PMI_GET_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_PMI_GET_CONFIGURATION IOCTL


## -description


The <b>IOCTL_PMI_GET_CONFIGURATION</b> request returns information about the current configuration of a power meter.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member of the I/O request packet (IRP) points to an initiator-allocated buffer that is used both as the input buffer and the output buffer for the request. On input, this buffer contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure in which the <b>Version</b> and <b>ConfigurationType</b> members are set to valid values. The <b>ConfigurationType</b> member contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> enumeration value that specifies the type of configuration information to be retrieved from the power meter. This value also determines the type of configuration information to be written to the output buffer.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IRP's current I/O stack location (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>) is set to the size in bytes of the buffer pointed to by the <b>AssociatedIrp.SystemBuffer</b> member. This size must be greater than or equal to <b>sizeof</b>(<b>PMI_CONFIGURATION</b>) or the request will fail with an error status of STATUS_INVALID_PARAMETER.


### -output-buffer

If the request completes successfully, the buffer pointed to by the <b>AssociatedIrp.SystemBuffer</b> member contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure. This structure contains the requested configuration information.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the IRP's current I/O stack location is set to the size in bytes of the buffer pointed to by the <b>AssociatedIrp.SystemBuffer</b> member. For the request to succeed, this size must be greater than or equal to <b>sizeof</b>(<b>PMI_CONFIGURATION</b>). Otherwise, the request will fail with an error status of STATUS_BUFFER_TOO_SMALL.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure.

The <b>Status</b> member is set to one of the following values:




**STATUS_BUFFER_TOO_SMALL**

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> is less than the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure.


**STATUS_INVALID_PARAMETER**

The initiator-allocated input buffer contains an invalid <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> value.


**STATUS_SUCCESS**

The WDM driver that supports the PMI interface has completed the IOCTL request successfully.


## -remarks



The <b>IOCTL_PMI_GET_CONFIGURATION</b> request queries the current configuration of the power meter. The input <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> enumeration value specifies the type of configuration data to be returned. The data type and contents of the output buffer vary based on the data requested.

The following table describes the type of data that is returned for the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> enumeration value.

<table>
<tr>
<th>PMI_CONFIGURATION_TYPE value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>PmiBudgetingConfiguration</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_budgeting_configuration">PMI_BUDGETING_CONFIGURATION</a> structure that contains information about the budgeting configuration of the power meter.

</td>
</tr>
<tr>
<td>
<b>PmiMeasurementConfiguration</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_measurement_configuration">PMI_MEASUREMENT_CONFIGURATION</a> structure that contains information about the measurement configuration of the power meter.

</td>
</tr>
<tr>
<td>
<b>PmiThresholdConfiguration</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_threshold_configuration">PMI_THRESHOLD_CONFIGURATION</a> structure that contains information about the threshold configuration of the power meter.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_budgeting_configuration">PMI_BUDGETING_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_capabilities_type">PMI_CAPABILITIES_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_measurement_configuration">PMI_MEASUREMENT_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_threshold_configuration">PMI_THRESHOLD_CONFIGURATION</a>
 

 

