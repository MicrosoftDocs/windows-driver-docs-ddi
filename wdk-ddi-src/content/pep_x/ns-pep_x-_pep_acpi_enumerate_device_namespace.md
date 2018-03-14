---
UID: NS:pep_x._PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
title: "_PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE"
author: windows-driver-content
description: The PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure contains an enumeration of the objects in the namespace of the device.
old-location: kernel\pep_acpi_enumerate_device_namespace.htm
old-project: kernel
ms.assetid: 61315EFB-DEA7-4CF2-97D3-EACD223AFB50
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, kernel.pep_acpi_enumerate_device_namespace, pepfx/PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, pepfx/PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, *PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, *PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
---

# _PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure


## -description


The <b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b> structure contains an enumeration of the objects in the namespace of the device.


## -syntax


````
typedef struct _PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE {
  PEPHANDLE                      DeviceHandle;
  SIZE_T                         TotalBufferSize;
  ULONG                          RequestFlags;
  NTSTATUS                       Status;
  ULONG                          ObjectCount;
  PEP_ACPI_OBJECT_NAME_WITH_TYPE Objects[ANYSIZE_ARRAY];
} PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, *PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE;
````


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.


### -field RequestFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_EDN_FLAG_NONE (0x0).


### -field Status

[out] An NTSTATUS value that indicates the status of the requested device-namespace enumeration. Set this member to STATUS_SUCCESS if the PEP succeeds in enumerating the objects in the device namespace. Set to STATUS_BUFFER_TOO_SMALL if the input value in the <b>TotalBufferSize</b> member indicates that the allocated buffer is not large enough to contain the <b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b> structure and <b>Objects</b> array.


### -field ObjectCount

[out] The number of elements in the <b>Objects</b> array.


### -field ObjectBufferSize

 


### -field Objects

[out] The first element in an array of <a href="..\pepfx\ns-pepfx-_pep_acpi_object_name_with_type.md">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a> structures that describe the objects in the ACPI namespace of the device. If this array contains more than one element, the additional array elements follow the end of the <b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b> structure.


#### - TotalBufferSize

[in, out] On input, the total size, in bytes, of the buffer that the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) allocated for this structure and for any <b>Objects</b> array elements that follow the structure. If the input value of <b>TotalBufferSize</b> is not large enough to contain this structure and all the <b>Objects</b> array elements, the PEP overwrites the input value with the required size and sets the <b>Status</b> member to STATUS_BUFFER_TOO_SMALL. For more information, see Remarks.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186658">PEP_NOTIFY_ACPI_ENUMERATE_DEVICE_NAMESPACE</a> notification. The <b>RequestFlags</b> and <b>TotalBufferSize</b> members contain input values supplied by PoFx when the notification is sent. The PEP may overwrite the <b>TotalBufferSize</b> input value with an output value if the input value is less than the required output buffer size. The <b>Status</b>, <b>ObjectCount</b>, and <b>Objects</b> members contain output values that the PEP writes to the structure.

If N is the number of objects listed in the ACPI namespace under this device, the PEP should verify that the storage allocated by PoFx for the <b>Objects</b> array is large enough to contain N array elements. If N &gt; 1, the additional N–1 array elements follow the end of the <b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b> structure. The buffer size required to contain the structure and additional array elements is calculated as follows:

<b>sizeof</b>
<b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b>
<b>sizeof</b>
<b>PEP_ACPI_OBJECT_NAME_WITH_TYPE</b>
If the input value specified in the <b>TotalBufferSize</b> member is less than the required size, the PEP overwrites the <b>TotalBufferSize</b> input value with the required size, and sets the <b>Status</b> member to STATUS_BUFFER_TOO_SMALL. In response, PoFx will allocate a buffer of the required size and send a second <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186658">PEP_NOTIFY_ACPI_ENUMERATE_DEVICE_NAMESPACE</a> notification to the PEP for this device.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_object_name_with_type.md">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186658">PEP_NOTIFY_ACPI_ENUMERATE_DEVICE_NAMESPACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

