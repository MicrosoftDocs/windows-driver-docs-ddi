---
UID: NC:pepfx.POFXCALLBACKCRITICALRESOURCE
title: POFXCALLBACKCRITICALRESOURCE
author: windows-driver-content
description: The TransitionCriticalResource routine changes the active/inactive state of a core system component.
old-location: kernel\transitioncriticalresource.htm
old-project: kernel
ms.assetid: 18CB1032-78CB-4D65-9077-02B89E9C31B4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.transitioncriticalresource, TransitionCriticalResource, TransitionCriticalResource routine [Kernel-Mode Driver Architecture], TransitionCriticalResource, POFXCALLBACKCRITICALRESOURCE, POFXCALLBACKCRITICALRESOURCE, pepfx/TransitionCriticalResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= HIGH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	pepfx.h
apiname:
-	TransitionCriticalResource
product: Windows
targetos: Windows
req.typenames: VPCI_PNP_ID, *PVPCI_PNP_ID
---

# POFXCALLBACKCRITICALRESOURCE callback


## -description


The <b>TransitionCriticalResource</b> routine changes the active/inactive state of a core system component.


## -prototype


````
POFXCALLBACKCRITICALRESOURCE TransitionCriticalResource;

VOID TransitionCriticalResource(
  _In_ POHANDLE DeviceHandle,
  _In_ ULONG    Component,
  _In_ BOOLEAN  Active
)
{ ... }
````


## -parameters




### -param DeviceHandle [in]

A POHANDLE value that represents the registration of the device with PoFx. The PEP previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


### -param Component [in]

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param Active [in]

Whether to transition the device from inactive to active, or vice versa. Set to TRUE to transition the device from inactive to active, or to FALSE to transition the device from active to inactive.


## -returns



None




## -remarks



This routine is implemented by the power management framework (PoFx) and is called by the platform extension plug-in (PEP). The <b>TransitionCriticalResource</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>TransitionCriticalResource</b> routine.

A PEP can call this routine at IRQL &lt;= HIGH_LEVEL.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a>



<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKCRITICALRESOURCE routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

