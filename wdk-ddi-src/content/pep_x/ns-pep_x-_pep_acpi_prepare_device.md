---
UID: NS:pep_x._PEP_ACPI_PREPARE_DEVICE
title: "_PEP_ACPI_PREPARE_DEVICE"
author: windows-driver-content
description: The PEP_ACPI_PREPARE_DEVICE structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device.
old-location: kernel\pep_acpi_prepare_device.htm
old-project: kernel
ms.assetid: F8D6680D-EFA7-4DED-B808-0E738A852641
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: "*PPEP_ACPI_PREPARE_DEVICE, PEP_ACPI_PREPARE_DEVICE, PEP_ACPI_PREPARE_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_PREPARE_DEVICE, PPEP_ACPI_PREPARE_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_PREPARE_DEVICE, kernel.pep_acpi_prepare_device, pepfx/PEP_ACPI_PREPARE_DEVICE, pepfx/PPEP_ACPI_PREPARE_DEVICE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_PREPARE_DEVICE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_PREPARE_DEVICE, *PPEP_ACPI_PREPARE_DEVICE
---

# _PEP_ACPI_PREPARE_DEVICE structure


## -description


The <b>PEP_ACPI_PREPARE_DEVICE</b> structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device.


## -struct-fields




### -field AcpiDeviceName

[in] A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure that contains the fully qualified BIOS name for the device. This name specifies the path and name of the device in the ACPI namespace. For more information, see <a href="https://msdn.microsoft.com/fe0553df-a5b9-46c4-8e1d-8b89a7d4ad67">Enumerating Child Devices and Control Methods</a>.


### -field InputFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_PREPARE_DEVICE_INPUT_FLAG_NONE (0x0).


### -field DeviceAccepted

[out] Whether the PEP is prepared to provide ACPI services for the device. Set this member to TRUE if the PEP is prepared to be the sole provider of ACPI services for this device, and to FALSE if it is not.


### -field OutputFlags

[out] A set of output flags. No flags are currently defined for this member. Set this member to PEP_ACPI_PREPARE_DEVICE_OUTPUT_FLAG_NONE (0x0).


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186686">PEP_NOTIFY_ACPI_PREPARE_DEVICE</a> notification. The <b>AcpiDeviceName</b> and <b>InputFlags</b> members of the structure contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>DeviceAccepted</b> and <b>OutputFlags</b> members contain output values that the PEP writes to the structure in response to the notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186686">PEP_NOTIFY_ACPI_PREPARE_DEVICE</a>
 

 

