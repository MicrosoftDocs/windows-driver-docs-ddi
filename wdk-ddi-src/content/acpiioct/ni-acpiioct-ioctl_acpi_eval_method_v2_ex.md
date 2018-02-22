---
UID: NI:acpiioct.IOCTL_ACPI_EVAL_METHOD_V2_EX
title: IOCTL_ACPI_EVAL_METHOD_V2_EX
author: windows-driver-content
description: The IOCTL_ACPI_EVAL_METHOD_V2_EX control code synchronously evaluates an ACPI control method that is supported by the device.
old-location: acpi\ioctl_acpi_eval_method_v2_ex.htm
old-project: acpi
ms.assetid: 0BD23D27-D9B0-462D-A38A-BC96A089E60F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: acpi.ioctl_acpi_eval_method_v2_ex, IOCTL_ACPI_EVAL_METHOD_V2_EX control code [ACPI Devices], IOCTL_ACPI_EVAL_METHOD_V2_EX, acpiioct/IOCTL_ACPI_EVAL_METHOD_V2_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709 and later versions.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	IOCTL_ACPI_EVAL_METHOD_V2_EX
product: Windows
targetos: Windows
req.typenames: "*PUNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS"
---

# IOCTL_ACPI_EVAL_METHOD_V2_EX IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


The <b>IOCTL_ACPI_EVAL_METHOD_V2_EX</b> control code synchronously evaluates an ACPI control method that is supported by the device.


## -ioctlparameters




### -input-buffer

An input buffer structure that depends on the type of input arguments to be passed to the control method.


### -input-buffer-length

The size, in bytes, of the input buffer.


### -output-buffer

An output buffer structure that contains the output arguments from the control method.


### -output-buffer-length

The size, in bytes, of the output buffer.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20IOCTL_ACPI_EVAL_METHOD_V2_EX control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

