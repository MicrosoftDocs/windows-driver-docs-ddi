---
UID: NS:pepfx._PEP_WORK_POWER_CONTROL
title: "_PEP_WORK_POWER_CONTROL"
author: windows-driver-content
description: The PEP_WORK_POWER_CONTROL structure contains the parameters for a power control request that the platform extension plug-in (PEP) sends directly to a processor driver.
old-location: kernel\pep_work_power_control.htm
old-project: kernel
ms.assetid: 84258422-A2AE-449F-97C8-41336FEA5D8B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPEP_WORK_POWER_CONTROL, ,, C, E, K, L, N, O, P, PEP_WORK_POWER_CONTROL, PEP_WORK_POWER_CONTROL structure [Kernel-Mode Driver Architecture], PPEP_WORK_POWER_CONTROL, PPEP_WORK_POWER_CONTROL structure pointer [Kernel-Mode Driver Architecture], R, T, W, _, _PEP_WORK_POWER_CONTROL, kernel.pep_work_power_control, pepfx/PEP_WORK_POWER_CONTROL, pepfx/PPEP_WORK_POWER_CONTROL"
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
-	PEP_WORK_POWER_CONTROL
product: Windows
targetos: Windows
req.typenames: PEP_WORK_POWER_CONTROL, *PPEP_WORK_POWER_CONTROL
---

# _PEP_WORK_POWER_CONTROL structure


## -description


The <b>PEP_WORK_POWER_CONTROL</b> structure contains the parameters for a <a href="https://msdn.microsoft.com/10A30691-CDF9-4B62-B6E8-790CA52C0E91">power control request</a> that the platform extension plug-in (PEP) sends directly to a processor driver.


## -syntax


````
typedef struct _PEP_WORK_POWER_CONTROL {
  POHANDLE DeviceHandle;
  LPCGUID  PowerControlCode;
  PVOID    RequestContext;
  PVOID    InBuffer;
  SIZE_T   InBufferSize;
  PVOID    OutBuffer;
  SIZE_T   OutBufferSize;
} PEP_WORK_POWER_CONTROL, *PPEP_WORK_POWER_CONTROL;
````


## -struct-fields




### -field DeviceHandle

A POHANDLE value that identifies the processor. The PEP received this handle in a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field PowerControlCode

[in] A pointer to a <a href="http://msdn.microsoft.com/library/windows/desktop/aa373931(v=vs.85).aspx">GUID</a> value that specifies the power control operation to perform.


### -field RequestContext

A pointer to a PEP-defined context value. The PEP might use this value to uniquely identify a power control request message (in case the PEP issues multiple requests with the same control code to the same device).


### -field InBuffer

[in] A pointer to a driver-allocated input buffer that contains the input parameters for this power control operation.


### -field InBufferSize

[in] The size in bytes of the buffer pointed to by <b>InBuffer</b>.


### -field OutBuffer

[in] A pointer to a driver-allocated output buffer to which the PEP writes the results of this power control operation.


### -field OutBufferSize

[in] The size in bytes of the buffer pointed to by <b>OutBuffer</b>.


## -remarks



The <b>PowerControl</b> member of the <a href="..\pep_x\ns-pep_x-_pep_work_information.md">PEP_WORK_INFORMATION</a> structure is a pointer to a <b>PEP_WORK_POWER_CONTROL</b> structure.

The PEP issues a power control request from a worker thread. The Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) forwards this request by calling the processor driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a> routine, if the driver implements this routine.




## -see-also

<a href="..\pep_x\ns-pep_x-_pep_work_information.md">PEP_WORK_INFORMATION</a>



<a href="http://msdn.microsoft.com/library/windows/desktop/aa373931(v=vs.85).aspx">GUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a>



<a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_WORK_POWER_CONTROL structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

