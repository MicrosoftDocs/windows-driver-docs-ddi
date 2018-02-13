---
UID: NS:pepfx._PEP_ACPI_UNREGISTER_DEVICE
title: "_PEP_ACPI_UNREGISTER_DEVICE"
author: windows-driver-content
description: The PEP_ACPI_UNREGISTER_DEVICE structure contains information about a device that has been unregistered from ACPI services.
old-location: kernel\pep_acpi_unregister_device.htm
old-project: kernel
ms.assetid: AA9D9AB3-B799-4D21-A418-D29360BBE605
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_ACPI_UNREGISTER_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_UNREGISTER_DEVICE, pepfx/PEP_ACPI_UNREGISTER_DEVICE, kernel.pep_acpi_unregister_device, PEP_ACPI_UNREGISTER_DEVICE, pepfx/PPEP_ACPI_UNREGISTER_DEVICE, *PPEP_ACPI_UNREGISTER_DEVICE, PPEP_ACPI_UNREGISTER_DEVICE, PEP_ACPI_UNREGISTER_DEVICE structure [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_UNREGISTER_DEVICE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_UNREGISTER_DEVICE, *PPEP_ACPI_UNREGISTER_DEVICE
---

# _PEP_ACPI_UNREGISTER_DEVICE structure


## -description


The <b>PEP_ACPI_UNREGISTER_DEVICE</b> structure contains information about a device that has been unregistered from ACPI services.


## -syntax


````
typedef struct _PEP_ACPI_UNREGISTER_DEVICE {
  PEPHANDLE DeviceHandle;
  ULONG     InputFlags;
} PEP_ACPI_UNREGISTER_DEVICE, *PPEP_ACPI_UNREGISTER_DEVICE;
````


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.


### -field InputFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_UNREGISTER_DEVICE_INPUT_FLAG_NONE (0x0).


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_NOTIFY_ACPI_UNREGISTER_DEVICE</a> notification. The <b>DeviceHandle</b> and <b>InputFlags</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> when this notification is sent.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_NOTIFY_ACPI_UNREGISTER_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_UNREGISTER_DEVICE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

