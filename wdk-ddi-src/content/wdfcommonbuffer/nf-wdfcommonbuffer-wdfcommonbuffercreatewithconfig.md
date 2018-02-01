---
UID: NF:wdfcommonbuffer.WdfCommonBufferCreateWithConfig
title: WdfCommonBufferCreateWithConfig function
author: windows-driver-content
description: The WdfCommonBufferCreateWithConfig method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously, and the method also specifies buffer configuration information.
old-location: wdf\wdfcommonbuffercreatewithconfig.htm
old-project: wdf
ms.assetid: 3ed8b7df-9c7d-44de-a49d-10221acf71e3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCommonBufferCreateWithConfig, wdfcommonbuffer/WdfCommonBufferCreateWithConfig, WdfCommonBufferCreateWithConfig method, wdf.wdfcommonbuffercreatewithconfig, kmdf.wdfcommonbuffercreatewithconfig, DFCommonBufferObjectRef_4e009b5f-a2a4-4be5-84d6-308c1558e702.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfCommonBufferCreateWithConfig
product: Windows
targetos: Windows
req.typenames: "*PWDF_CHILD_RETRIEVE_INFO, WDF_CHILD_RETRIEVE_INFO"
req.product: Windows 10 or later.
---

# WdfCommonBufferCreateWithConfig function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfCommonBufferCreateWithConfig</b> method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously, and the method also specifies buffer configuration information.


## -syntax


````
NTSTATUS WdfCommonBufferCreateWithConfig(
  _In_     WDFDMAENABLER             DmaEnabler,
  _In_     size_t                    Length,
  _In_     PWDF_COMMON_BUFFER_CONFIG Config,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES    Attributes,
  _Out_    WDFCOMMONBUFFER           *CommonBuffer
);
````


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained by a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.  


### -param Length [in]

The desired size, in bytes, of the new buffer.


### -param Config [in]

A pointer to a <a href="..\wdfcommonbuffer\ns-wdfcommonbuffer-_wdf_common_buffer_config.md">WDF_COMMON_BUFFER_CONFIG</a> structure that contains configuration information about the buffer.


### -param Attributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the common buffer object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


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

Additionally, <b>WdfCommonBufferCreateWithConfig</b> enables your driver to specify a buffer alignment requirement for the buffer. The buffer alignment requirement overrides the buffer alignment requirement that the driver specified when it called <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetalignmentrequirement.md">WdfDeviceSetAlignmentRequirement</a>. Your driver can use <b>WdfCommonBufferCreateWithConfig</b>, instead of <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffercreate.md">WdfCommonBufferCreate</a>, if you want the driver to create a buffer that has a different alignment requirement than the one that <b>WdfDeviceSetAlignmentRequirement</b> specified.

After your driver calls <b>WdfCommonBufferCreateWithConfig</b>, the driver must:
<ul>
<li>
Call <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md">WdfCommonBufferGetAlignedVirtualAddress</a> to obtain the buffer's virtual address, which the driver can use.

</li>
<li>
Call <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md">WdfCommonBufferGetAlignedLogicalAddress</a> to obtain the buffer's logical address, which the device can use.

</li>
</ul>A driver typically calls <b>WdfCommonBufferCreateWithConfig</b> from within its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. 

The operating system determines whether to enable cached memory in the common buffer that is to be allocated. That decision is based on the processor architecture and device bus.


On computers with x86-based, x64-based, and Itanium-based processors, cached memory is enabled.
On computers with ARM or ARM 64-based processors, the operating system does not automatically enable cached memory for all devices. The system relies on the ACPI_CCA method for each device to determine whether the device is cache-coherent.

For more information about common buffers, see <a href="https://msdn.microsoft.com/81a56f62-917e-4798-b2cc-6469c802fab8">Using Common Buffers</a>




## -see-also

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md">WdfCommonBufferGetAlignedVirtualAddress</a>

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetalignmentrequirement.md">WdfDeviceSetAlignmentRequirement</a>

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffercreate.md">WdfCommonBufferCreate</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md">WdfCommonBufferGetAlignedLogicalAddress</a>

<a href="..\wdfcommonbuffer\ns-wdfcommonbuffer-_wdf_common_buffer_config.md">WDF_COMMON_BUFFER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCommonBufferCreateWithConfig method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

