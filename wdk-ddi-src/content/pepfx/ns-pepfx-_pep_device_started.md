---
UID: NS:pepfx._PEP_DEVICE_STARTED
title: "_PEP_DEVICE_STARTED"
author: windows-driver-content
description: The PEP_DEVICE_STARTED structure identifies a device whose driver has completed its registration with the Windows power management framework (PoFx).
old-location: kernel\pep_device_started.htm
old-project: kernel
ms.assetid: 02A30A9F-A27D-492E-8FB3-D8CB34D51D5A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_DEVICE_STARTED structure pointer [Kernel-Mode Driver Architecture], pepfx/PPEP_DEVICE_STARTED, _PEP_DEVICE_STARTED, *PPEP_DEVICE_STARTED, PEP_DEVICE_STARTED, kernel.pep_device_started, PEP_DEVICE_STARTED structure [Kernel-Mode Driver Architecture], pepfx/PEP_DEVICE_STARTED, PPEP_DEVICE_STARTED
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
-	PEP_DEVICE_STARTED
product: Windows
targetos: Windows
req.typenames: "*PPEP_DEVICE_STARTED, PEP_DEVICE_STARTED"
---

# _PEP_DEVICE_STARTED structure


## -description


The <b>PEP_DEVICE_STARTED</b> structure identifies a device whose driver has completed its registration with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).


## -syntax


````
typedef struct _PEP_DEVICE_STARTED {
  PEPHANDLE DeviceHandle;
} PEP_DEVICE_STARTED, *PPEP_DEVICE_STARTED;
````


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186714">PEP_DPM_DEVICE_STARTED</a> notification. The <b>DeviceHandle</b> member of this structure contains an input value that is supplied by PoFx.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186714">PEP_DPM_DEVICE_STARTED</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_DEVICE_STARTED structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

