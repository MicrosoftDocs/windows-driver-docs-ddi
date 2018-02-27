---
UID: NS:pepfx._PEP_WORK_ACPI_NOTIFY
title: "_PEP_WORK_ACPI_NOTIFY"
author: windows-driver-content
description: The PEP_WORK_ACPI_NOTIFY structure contains the ACPI Notify code for a device that has generated a hardware event.
old-location: kernel\pep_work_acpi_notify.htm
old-project: kernel
ms.assetid: DFFDDF13-B8C7-4AB0-B2C9-9F34D19B21AE
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_WORK_ACPI_NOTIFY, PEP_WORK_ACPI_NOTIFY, PEP_WORK_ACPI_NOTIFY structure [Kernel-Mode Driver Architecture], PPEP_WORK_ACPI_NOTIFY, PPEP_WORK_ACPI_NOTIFY structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_ACPI_NOTIFY, kernel.pep_work_acpi_notify, pepfx/PEP_WORK_ACPI_NOTIFY, pepfx/PPEP_WORK_ACPI_NOTIFY"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_WORK_ACPI_NOTIFY
product: Windows
targetos: Windows
req.typenames: PEP_WORK_ACPI_NOTIFY, *PPEP_WORK_ACPI_NOTIFY
---

# _PEP_WORK_ACPI_NOTIFY structure


## -description


The <b>PEP_WORK_ACPI_NOTIFY</b> structure contains the ACPI Notify code for a device that has generated a hardware event.


## -syntax


````
typedef struct _PEP_WORK_ACPI_NOTIFY {
  POHANDLE DeviceHandle;
  ULONG    NotifyCode;
} PEP_WORK_ACPI_NOTIFY, *PPEP_WORK_ACPI_NOTIFY;
````


## -struct-fields




### -field DeviceHandle

A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification in which the PEP elected to provide ACPI services for the device.


### -field NotifyCode

The Notify code. For a list of Notify codes and their meanings, see section 5.6.6, "Device Object Notifications", of the Advanced Configuration and Power Interface Specification, Revision 5.0 (<a href="http://www.acpi.info">ACPI 5.0 specification</a>).


## -remarks



The <b>AcpiNotify</b> member of the <a href="..\pepfx\ns-pepfx-_pep_work_information.md">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_ACPI_NOTIFY</b> structure.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_work_information.md">PEP_WORK_INFORMATION</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_WORK_ACPI_NOTIFY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

