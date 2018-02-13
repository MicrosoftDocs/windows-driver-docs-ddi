---
UID: NS:pepfx._PEP_REGISTER_CRASHDUMP_DEVICE
title: "_PEP_REGISTER_CRASHDUMP_DEVICE"
author: windows-driver-content
description: The PEP_REGISTER_CRASHDUMP_DEVICE structure provides a callback routine to turn on a crash-dump device.
old-location: kernel\pep_register_crashdump_device.htm
old-project: kernel
ms.assetid: 207EEFBF-289F-4973-9183-7D87C0BAE09A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: pepfx/PPEP_REGISTER_CRASHDUMP_DEVICE, pepfx/PEP_REGISTER_CRASHDUMP_DEVICE, PEP_REGISTER_CRASHDUMP_DEVICE structure [Kernel-Mode Driver Architecture], PEP_REGISTER_CRASHDUMP_DEVICE, *PPEP_REGISTER_CRASHDUMP_DEVICE, PPEP_REGISTER_CRASHDUMP_DEVICE, kernel.pep_register_crashdump_device, PPEP_REGISTER_CRASHDUMP_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_REGISTER_CRASHDUMP_DEVICE
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
-	PEP_REGISTER_CRASHDUMP_DEVICE
product: Windows
targetos: Windows
req.typenames: PEP_REGISTER_CRASHDUMP_DEVICE, *PPEP_REGISTER_CRASHDUMP_DEVICE
---

# _PEP_REGISTER_CRASHDUMP_DEVICE structure


## -description


The <b>PEP_REGISTER_CRASHDUMP_DEVICE</b> structure provides a callback routine to turn on a crash-dump device.


## -syntax


````
typedef struct _PEP_REGISTER_CRASHDUMP_DEVICE {
  PPEPCALLBACKPOWERONCRASHDUMPDEVICE PowerOnDumpDeviceCallback;
  PEPHANDLE                          DeviceHandle;
} PEP_REGISTER_CRASHDUMP_DEVICE, *PPEP_REGISTER_CRASHDUMP_DEVICE;
````


## -struct-fields




### -field PowerOnDumpDeviceCallback

[out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186875">PowerOnDumpDeviceCallback</a> callback routine that is implemented by the platform extension plug-in (PEP). This routine handles requests from the Windows kernel to turn on the crash-dump device so that a crash dump can be saved. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551880">Kernel-Mode Dump Files</a>.


### -field DeviceHandle

[in] A PEPHANDLE value that identifies the crash-dump device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a> notification. The <b>DeviceHandle</b> member of the structure contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>PowerOnDumpDeviceCallbackmember</b> contains an output value that the PEP writes to the structure in response to the notification.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186875">PowerOnDumpDeviceCallback</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_REGISTER_CRASHDUMP_DEVICE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

