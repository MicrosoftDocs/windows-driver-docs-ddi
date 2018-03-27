---
UID: NS:pepfx._PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
title: "_PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES"
author: windows-driver-content
description: The PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use.
old-location: kernel\pep_acpi_translated_device_control_resources.htm
old-project: kernel
ms.assetid: 1274EF11-6A0D-4464-992D-4E27C981971F
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure [Kernel-Mode Driver Architecture], _PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, kernel.pep_acpi_translated_device_control_resources, pepfx/PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
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
-	PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, *PPEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
---

# _PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure


## -description


The <b>PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</b> structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.


### -field RequestFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_TDCR_FLAG_NONE (0x0).


### -field Status

[out] An NTSTATUS value that indicates the status of the resource translation. The PEP sets this member to STATUS_SUCCESS to indicate that the PEP successfully received the translated resources. Otherwise, the PEP sets this member to an appropriate error status code.


### -field TranslatedResourcesSize

 


### -field TranslatedResources

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a> structure that serves as the header for the resource list. The remainder of the resource list immediately follows this header.


#### - ResourceBufferSize

[in] The size in bytes of the input buffer that contains both this structure and the resource-list data that follows this structure.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186698">PEP_NOTIFY_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</a> notification to provide the PEP with a list of translated power control resources. The <b>RequestFlags</b>, <b>ResourceBufferSize</b>, and <b>TranslatedResources</b> members of the structure contain input values that the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) supplies when this notification is sent. The <b>Status</b> member contains an output value that the PEP writes to the structure in response to the notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186698">PEP_NOTIFY_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

