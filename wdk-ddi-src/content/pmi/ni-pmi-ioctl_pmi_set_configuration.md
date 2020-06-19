---
UID: NI:pmi.IOCTL_PMI_SET_CONFIGURATION
title: IOCTL_PMI_SET_CONFIGURATION (pmi.h)
description: The IOCTL_PMI_SET_CONFIGURATION request sets the configuration data for a power meter.
old-location: powermeter\ioctl_pmi_set_configuration.htm
tech.root: powermeter
ms.assetid: c8eff87f-b8af-4876-9327-545eeff958c3
ms.date: 05/08/2018
keywords: ["IOCTL_PMI_SET_CONFIGURATION IOCTL"]
ms.keywords: IOCTL_PMI_SET_CONFIGURATION, IOCTL_PMI_SET_CONFIGURATION control, IOCTL_PMI_SET_CONFIGURATION control code [Power Metering and Budgeting Devices], PowerMeterRef_6bfb518f-962c-48c1-b94e-711679fd8057.xml, pmi/IOCTL_PMI_SET_CONFIGURATION, powermeter.ioctl_pmi_set_configuration
f1_keywords:
 - "pmi/IOCTL_PMI_SET_CONFIGURATION"
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
- IOCTL_PMI_SET_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_PMI_SET_CONFIGURATION IOCTL


## -description


The <b>IOCTL_PMI_SET_CONFIGURATION</b> request sets the configuration data for a power meter.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member of the I/O request packet (IRP) points to an initiator-allocated input buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure. This structure contains the configuration data.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IRP's current I/O stack location (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>) is set to the size in bytes of the input buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member. This size must be greater than or equal to <b>sizeof</b>(<b>PMI_CONFIGURATION</b>) or the request fails with an error status of STATUS_BUFFER_TOO_SMALL.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure.

The <b>Status</b> member is set to one of the following values:




**STATUS_BUFFER_TOO_SMALL**

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> is less than the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure. 


**STATUS_SUCCESS**

The WDM driver that supports the PMI interface has completed the IOCTL request successfully. 


## -remarks



The <b>IOCTL_PMI_SET_CONFIGURATION</b> request sets the configuration parameters for the power meter. The <b>AssociatedIrp.SystemBuffer</b> member of the IRP references a buffer that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure. The <b>ConfigurationType</b> member of this structure contains information about the type of PMI configuration data to set in the power meter.

Only PMI configuration data that the power meter supports with read/write permissions can be changed by using a set request of <b>IOCTL_PMI_SET_CONFIGURATION</b>. A set request of <b>IOCTL_PMI_SET_CONFIGURATION</b> to change read-only PMI configuration data will fail, and the data will not be changed on the power meter.

<div class="alert"><b>Note</b>  Beginning with Windows 7 and Windows Server 2008 R2, the power meter can also support read/write permissions to its budgeting information. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>
 

 

