---
UID: NS:pepfx._PEP_REGISTER_DEBUGGER
title: "_PEP_REGISTER_DEBUGGER"
author: windows-driver-content
description: The PEP_REGISTER_DEBUGGER structure identifies a registered device that is a core system resource that provides debugger transport.
old-location: kernel\pep_register_debugger.htm
old-project: kernel
ms.assetid: 3B0240AB-4599-4F21-8CBB-14A4A60D3EFD
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: pepfx/PEP_REGISTER_DEBUGGER, PPEP_REGISTER_DEBUGGER structure pointer [Kernel-Mode Driver Architecture], _PEP_REGISTER_DEBUGGER, PPEP_REGISTER_DEBUGGER, kernel.pep_register_debugger, PEP_REGISTER_DEBUGGER structure [Kernel-Mode Driver Architecture], pepfx/PPEP_REGISTER_DEBUGGER, *PPEP_REGISTER_DEBUGGER, PEP_REGISTER_DEBUGGER
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
-	PEP_REGISTER_DEBUGGER
product: Windows
targetos: Windows
req.typenames: PEP_REGISTER_DEBUGGER, *PPEP_REGISTER_DEBUGGER
---

# _PEP_REGISTER_DEBUGGER structure


## -description


The <b>PEP_REGISTER_DEBUGGER</b> structure identifies a registered device that is a core system resource that provides debugger transport.


## -syntax


````
typedef struct _PEP_REGISTER_DEBUGGER {
  PEPHANDLE DeviceHandle;
} PEP_REGISTER_DEBUGGER, *PPEP_REGISTER_DEBUGGER;
````


## -struct-fields




### -field DeviceHandle

[in] A <b>PEPHANDLE</b> value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186850">PEP_DPM_REGISTER_DEBUGGER</a> notification. The <b>DeviceHandle</b> member contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186850">PEP_DPM_REGISTER_DEBUGGER</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_REGISTER_DEBUGGER structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

