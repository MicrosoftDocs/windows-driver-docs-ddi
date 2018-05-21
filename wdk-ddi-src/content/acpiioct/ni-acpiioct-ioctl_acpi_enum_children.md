---
UID: NI:acpiioct.IOCTL_ACPI_ENUM_CHILDREN
title: IOCTL_ACPI_ENUM_CHILDREN
author: windows-driver-content
description: The IOCTL_ACPI_ENUM_CHILDREN device control request can be used to enumerate the path and name of devices or named child objects in the ACPI namespace of the device to which this request is sent.
old-location: acpi\ioctl_acpi_enum_children.htm
old-project: acpi
ms.assetid: 86d713e0-ec1e-4417-9ff7-8574bd040a6e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_ACPI_ENUM_CHILDREN, IOCTL_ACPI_ENUM_CHILDREN control, IOCTL_ACPI_ENUM_CHILDREN control code [ACPI Devices], acpi-meth-eval-ref_243e3f53-71b8-4090-bcf1-48b0c5634b5e.xml, acpi.ioctl_acpi_enum_children, acpiioct/IOCTL_ACPI_ENUM_CHILDREN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Acpiioct.h
api_name:
-	IOCTL_ACPI_ENUM_CHILDREN
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_ACPI_ENUM_CHILDREN IOCTL


## -description


The IOCTL_ACPI_ENUM_CHILDREN device control request can be used to enumerate the path and name of devices or named child objects in the ACPI namespace of the device to which this request is sent. A driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a> and pass the following input and output parameters to build this request. 


## -ioctlparameters




### -input-buffer

Set the <b>IoBuildDeviceIoControlRequest</b> input parameters as follows:

<ul>
<li>
<i>IoControlCode</i> is set to IOCTL_ACPI_ENUM_CHILDREN.

</li>
<li>
<i>DeviceObject</i> is set to a pointer to the physical device object (PDO) of the device.

</li>
<li>
<i>InputBuffer</i> is set to a pointer to a variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536110">ACPI_ENUM_CHILDREN_INPUT_BUFFER</a> structure.

</li>
<li>
<i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.

</li>
<li>
<i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.

</li>
<li>
<i>InternalDeviceIoControl</i> is set to <b>FALSE</b>.

</li>
<li>
<i>Event</i> is set to a pointer to a caller-allocated and initialized event object.

</li>
</ul>

### -input-buffer-length

<i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.


### -output-buffer

Set the <b>IoBuildDeviceIoControlRequest</b> output parameters as follows:

<ul>
<li>
<i>OutputBuffer</i> supplies a pointer to a variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536112">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a> structure in which the ACPI driver returns the path and name of the enumerated child devices.

</li>
<li>
<i>IoStatusBlock</i> is set to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure.

</li>
</ul>

### -output-buffer-length

<i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request succeeds, <i>IoStatusBlock</i>-&gt;<b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain the paths and names of all the enumerated child objects, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW and <i>OutputBuffer</i>-&gt;<b>NumberOfChildren</b> is set to the required length of the output buffer.

If the request succeeds, the <i>IoStatusBlock</i>-&gt;<b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.


## -remarks



IOCTL_ACPI_ENUM_CHILDREN returns a variable-length ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure that contains an array of variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> structures, each of which returns the fully qualified path and name of an object in the ACPI namespace of the device to which the request was sent. The objects that this request enumerates depends on the setting of the <b>Flags</b> member of the supplied input structure ACPI_ENUM_CHILDREN_INPUT_BUFFER, as follows:



If the output buffer that the driver allocates is not large enough to return all requested child names, the ACPI driver does not return any child names and sets the <b>Status</b> member of the IO_STATUS_BLOCK for the request to STATUS_BUFFER_OVERFLOW. In this case, if the size, in bytes, of the output buffer is at least <b>sizeof</b>(ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE), the ACPI driver also sets <i>NumberOfChildren</i> to the size, in bytes, that is required to retrieve the requested paths and names. 

A driver typically would use a sequence of two IOCTL_ACPI_ENUM_CHILDREN requests to enumerate the child objects of interest. The driver sends the first request to obtain the size of the output buffer that is required to contain the path and name of all the requested objects. The driver sends the second request to return the path and name of the objects in the output buffer. 

For more information about how to enumerate child devices of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.

IOCTL_ACPI_ENUM_CHILDREN can be used only at IRQL&lt; DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536110">ACPI_ENUM_CHILDREN_INPUT_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536112">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a>
 

 

