---
UID: NF:wdfcommonbuffer.WdfCommonBufferCreate
title: WdfCommonBufferCreate function (wdfcommonbuffer.h)
description: The WdfCommonBufferCreate method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously.
old-location: wdf\wdfcommonbuffercreate.htm
tech.root: wdf
ms.assetid: 05e092fe-fa70-47b7-af8d-c6e27847a6ac
ms.date: 02/26/2018
ms.keywords: DFCommonBufferObjectRef_2ef72eb3-fa4c-40f8-aa73-54bb5dcb9e0c.xml, WdfCommonBufferCreate, WdfCommonBufferCreate method, kmdf.wdfcommonbuffercreate, wdf.wdfcommonbuffercreate, wdfcommonbuffer/WdfCommonBufferCreate
ms.topic: function
req.header: wdfcommonbuffer.h
req.include-header: WdfCommonBuffer.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
- WdfCommonBufferCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCommonBufferCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCommonBufferCreate</b> method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously.


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>.  


### -param Length [in]

The desired size, in bytes, of the new buffer.


### -param Attributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the common buffer object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param CommonBuffer [out]

A pointer to a WDFCOMMONBUFFER-typed variable that receives a handle to a common buffer object.


## -returns



<b>WdfCommonBufferCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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



The <b>WdfCommonBufferCreate</b> method allocates memory and maps it so that both the driver and a device can access it simultaneously for DMA operations. After your driver calls <b>WdfCommonBufferCreate</b>, the driver must:

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545820">WdfCommonBufferGetAlignedVirtualAddress</a> to obtain the buffer's virtual address, which the driver can use.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545814">WdfCommonBufferGetAlignedLogicalAddress</a> to obtain the buffer's logical address, which the device can use.

</li>
</ul>
A driver typically calls <b>WdfCommonBufferCreate</b> from within its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. 

Before the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>, it can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a> to set a buffer alignment requirement. If the driver does not call <b>WdfDeviceSetAlignmentRequirement</b>, buffers are aligned on word boundaries. If your driver creates multiple DMA enablers, each with a different buffer alignment requirement, the driver can call <b>WdfDeviceSetAlignmentRequirement</b> before each call to <b>WdfDmaEnablerCreate</b>.

To create a common buffer that has an alignment requirement that is different from the alignment requirement that the driver specified with <a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545805">WdfCommonBufferCreateWithConfig</a> instead of <b>WdfCommonBufferCreate</b>.

The operating system determines whether to enable cached memory in the common buffer that is to be allocated. That decision is based on the processor architecture and device bus.


On computers with x86-based, x64-based, and Itanium-based processors, cached memory is enabled.
On computers with ARM or ARM 64-based processors, the operating system does not automatically enable cached memory for all devices. The system relies on the ACPI_CCA method for each device to determine whether the device is cache-coherent.

The DMA enabler object that the <i>DmaEnabler</i> parameter of <b>WdfCommonBufferCreate</b> specifies becomes the parent object for the new common buffer object. The driver cannot change this parent, and the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>. The framework deletes each common buffer object when it deletes the parent DMA enabler object.

For more information about common buffers, see <a href="https://msdn.microsoft.com/81a56f62-917e-4798-b2cc-6469c802fab8">Using Common Buffers</a>.


#### Examples

The following code example shows how to obtain a common buffer. The example stores information about the common buffer in driver-defined context space that is identified by the <b>DevExt</b> pointer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DevExt->CommonBufferSize = sizeof(COMMON_BUFFER_STRUCT);  // Your structure size
status = WdfCommonBufferCreate(
                               DevExt->DmaEnabler,
                               DevExt->CommonBufferSize,
                               WDF_NO_OBJECT_ATTRIBUTES,
                               &DevExt->CommonBuffer
                               );
if (status == STATUS_SUCCESS) {
    DevExt->CommonBufferBaseVA = 
        WdfCommonBufferGetAlignedVirtualAddress(DevExt->CommonBuffer);
    DevExt->CommonBufferBaseLA =
        WdfCommonBufferGetAlignedLogicalAddress(DevExt->CommonBuffer); 
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545805">WdfCommonBufferCreateWithConfig</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545814">WdfCommonBufferGetAlignedLogicalAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545820">WdfCommonBufferGetAlignedVirtualAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546861">WdfDeviceSetAlignmentRequirement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>
 

 

