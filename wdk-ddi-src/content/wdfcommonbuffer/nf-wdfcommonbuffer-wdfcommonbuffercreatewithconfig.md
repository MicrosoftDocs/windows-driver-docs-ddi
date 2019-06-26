---
UID: NF:wdfcommonbuffer.WdfCommonBufferCreateWithConfig
title: WdfCommonBufferCreateWithConfig function (wdfcommonbuffer.h)
description: The WdfCommonBufferCreateWithConfig method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously, and the method also specifies buffer configuration information.
old-location: wdf\wdfcommonbuffercreatewithconfig.htm
tech.root: wdf
ms.assetid: 3ed8b7df-9c7d-44de-a49d-10221acf71e3
ms.date: 02/26/2018
ms.keywords: DFCommonBufferObjectRef_4e009b5f-a2a4-4be5-84d6-308c1558e702.xml, WdfCommonBufferCreateWithConfig, WdfCommonBufferCreateWithConfig method, kmdf.wdfcommonbuffercreatewithconfig, wdf.wdfcommonbuffercreatewithconfig, wdfcommonbuffer/WdfCommonBufferCreateWithConfig
ms.topic: function
req.header: wdfcommonbuffer.h
req.include-header: WdfCommonBuffer.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.1
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfCommonBufferCreateWithConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCommonBufferCreateWithConfig function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCommonBufferCreateWithConfig</b> method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously, and the method also specifies buffer configuration information.


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>.  


### -param Length [in]

The desired size, in bytes, of the new buffer.


### -param Config [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/ns-wdfcommonbuffer-_wdf_common_buffer_config">WDF_COMMON_BUFFER_CONFIG</a> structure that contains configuration information about the buffer.


### -param Attributes [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the common buffer object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param CommonBuffer [out]

A pointer to a WDFCOMMONBUFFER-typed variable that receives a handle to a common buffer object.


## -returns



<b>WdfCommonBufferCreateWithConfig</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The driver supplied an invalid parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate a common buffer object, or the system could not allocate a buffer.

</td>
</tr>
</table>
 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfCommonBufferCreateWithConfig</b> method allocates memory and maps it so that both the driver and a device can access it simultaneously for DMA operations. 

Additionally, <b>WdfCommonBufferCreateWithConfig</b> enables your driver to specify a buffer alignment requirement for the buffer. The buffer alignment requirement overrides the buffer alignment requirement that the driver specified when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicesetalignmentrequirement">WdfDeviceSetAlignmentRequirement</a>. Your driver can use <b>WdfCommonBufferCreateWithConfig</b>, instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffercreate">WdfCommonBufferCreate</a>, if you want the driver to create a buffer that has a different alignment requirement than the one that <b>WdfDeviceSetAlignmentRequirement</b> specified.

After your driver calls <b>WdfCommonBufferCreateWithConfig</b>, the driver must:

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress">WdfCommonBufferGetAlignedVirtualAddress</a> to obtain the buffer's virtual address, which the driver can use.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress">WdfCommonBufferGetAlignedLogicalAddress</a> to obtain the buffer's logical address, which the device can use.

</li>
</ul>
A driver typically calls <b>WdfCommonBufferCreateWithConfig</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. 

The operating system determines whether to enable cached memory in the common buffer that is to be allocated. That decision is based on the processor architecture and device bus.


On computers with x86-based, x64-based, and Itanium-based processors, cached memory is enabled.
On computers with ARM or ARM 64-based processors, the operating system does not automatically enable cached memory for all devices. The system relies on the ACPI_CCA method for each device to determine whether the device is cache-coherent.

For more information about common buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-common-buffers">Using Common Buffers</a>



#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/ns-wdfcommonbuffer-_wdf_common_buffer_config">WDF_COMMON_BUFFER_CONFIG</a> structure and then creates a 10-byte buffer that is aligned on a 32-byte boundary.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_COMMON_BUFFER_CONFIG  commonBufConfig;
WDFCOMMONBUFFER  commonBuffer;

WDF_COMMON_BUFFER_CONFIG_INIT(
                              &commonBufConfig,
                              FILE_32_BYTE_ALIGNMENT
                              );

status = WdfCommonBufferCreateWithConfig(
                                         DmaEnabler,
                                         10,
                                         &commonBufConfig,
                                         WDF_NO_OBJECT_ATTRIBUTES,
                                         &commonBuffer
                                         );
if (!NT_SUCCESS (status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/ns-wdfcommonbuffer-_wdf_common_buffer_config">WDF_COMMON_BUFFER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffercreate">WdfCommonBufferCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress">WdfCommonBufferGetAlignedLogicalAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress">WdfCommonBufferGetAlignedVirtualAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicesetalignmentrequirement">WdfDeviceSetAlignmentRequirement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>
 

 

