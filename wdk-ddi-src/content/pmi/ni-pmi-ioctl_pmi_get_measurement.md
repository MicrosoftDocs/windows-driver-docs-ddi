---
UID: NI:pmi.IOCTL_PMI_GET_MEASUREMENT
title: IOCTL_PMI_GET_MEASUREMENT (pmi.h)
description: The IOCTL_PMI_GET_MEASUREMENT request returns the current measurement data from a power meter.
old-location: powermeter\ioctl_pmi_get_measurement.htm
tech.root: powermeter
ms.assetid: 2f479147-cccb-44c8-bc86-37c6731cb95b
ms.date: 05/08/2018
ms.keywords: IOCTL_PMI_GET_MEASUREMENT, IOCTL_PMI_GET_MEASUREMENT control, IOCTL_PMI_GET_MEASUREMENT control code [Power Metering and Budgeting Devices], PowerMeterRef_2317a4b3-7909-4c52-a012-39c892a39154.xml, pmi/IOCTL_PMI_GET_MEASUREMENT, powermeter.ioctl_pmi_get_measurement
f1_keywords:
 - "pmi/IOCTL_PMI_GET_MEASUREMENT"
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
- IOCTL_PMI_GET_MEASUREMENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_PMI_GET_MEASUREMENT IOCTL


## -description


The <b>IOCTL_PMI_GET_MEASUREMENT</b> request returns the current measurement data from a power meter.


## -ioctlparameters




### -input-buffer

The initiator-allocated output buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member of the IRP.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the IRP's current I/O stack location (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>) is set to the size in bytes of the initiator-allocated output buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member of the IRP. This size must be greater than or equal to <b>sizeof</b>(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_measurement_data">PMI_MEASUREMENT_DATA</a>) or the request fails with an error status of STATUS_BUFFER_TOO_SMALL.


### -output-buffer

If the request completes successfully, the output buffer pointed to by the <b>AssociatedIrp.SystemBuffer</b> member contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_measurement_data">PMI_MEASUREMENT_DATA</a> structure. This structure contains the requested measurement data.


### -output-buffer-length

The size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_measurement_data">PMI_MEASUREMENT_DATA</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_measurement_data">PMI_MEASUREMENT_DATA</a> structure.

The <b>Status</b> member is set to one of the following values:




#### -STATUS_BUFFER_TOO_SMALL

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> is less than the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_measurement_data">PMI_MEASUREMENT_DATA</a> structure.


#### -STATUS_SUCCESS

The WDM driver that supports the PMI interface has completed the IOCTL request successfully.


## -remarks



The <b>IOCTL_PMI_GET_MEASUREMENT</b> request queries the current measurement data from the power meter. This measurement data is sampled and averaged based on the power meter's measurement configuration parameters. The measurement configuration parameters are queried through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a> request with an input <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> value of <b>PmiMeasurementConfiguration</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_measurement_data">PMI_MEASUREMENT_DATA</a>
 

 

