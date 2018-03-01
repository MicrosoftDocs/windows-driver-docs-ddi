---
UID: NS:pep_x._PEP_REGISTER_DEVICE_V2
title: "_PEP_REGISTER_DEVICE_V2"
author: windows-driver-content
description: The PEP_REGISTER_DEVICE_V2 structure describes a device whose driver stack has just registered with the Windows power management framework (PoFx).
old-location: kernel\pep_register_device_v2.htm
old-project: kernel
ms.assetid: A1363B34-CC5C-482E-8E8D-62D7263545E3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_REGISTER_DEVICE, *PPEP_REGISTER_DEVICE_V2, PEP_REGISTER_DEVICE, PEP_REGISTER_DEVICE_V2, PEP_REGISTER_DEVICE_V2 structure [Kernel-Mode Driver Architecture], PPEP_REGISTER_DEVICE_V2, PPEP_REGISTER_DEVICE_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_REGISTER_DEVICE_V2, kernel.pep_register_device_v2, pepfx/PEP_REGISTER_DEVICE_V2, pepfx/PPEP_REGISTER_DEVICE_V2"
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_REGISTER_DEVICE_V2
product: Windows
targetos: Windows
req.typenames: PEP_REGISTER_DEVICE_V2, *PPEP_REGISTER_DEVICE_V2, PEP_REGISTER_DEVICE_V2, *PPEP_REGISTER_DEVICE_V2
---

# _PEP_REGISTER_DEVICE_V2 structure


## -description


The <b>PEP_REGISTER_DEVICE_V2</b> structure describes a device whose driver stack has just registered with the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).


## -syntax


````
typedef struct _PEP_REGISTER_DEVICE_V2 {
  PCUNICODE_STRING           DeviceId;
  POHANDLE                   KernelHandle;
  PPEP_DEVICE_REGISTER_V2    Register;
  PEPHANDLE                  DeviceHandle;
  PEP_DEVICE_ACCEPTANCE_TYPE DeviceAccepted;
} PEP_REGISTER_DEVICE_V2, *PPEP_REGISTER_DEVICE_V2;
````


## -struct-fields




### -field DeviceId

[in] A string that uniquely identifies the device. This member is a pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/device-identification-strings">device identification string</a>.


### -field KernelHandle

[in] A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


### -field Register

[in] A pointer to a <a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a> structure that describes the power management attributes of all the components in the device. For more information, see Remarks.


### -field DeviceHandle

[out] A PEPHANDLE value that the PEP creates to identify this device.  PoFx will use this handle to identify the device in future <a href="https://msdn.microsoft.com/library/windows/hardware/mt186631">device power management (DPM) notifications</a>.


### -field DeviceAccepted

[out] A <a href="..\pepfx\ne-pepfx-_pep_device_acceptance_type.md">PEP_DEVICE_ACCEPTANCE_TYPE</a> enumeration value that indicates whether the PEP claims ownership of the device. The PEP that claims ownership is responsible for handling DPM notifications for the device.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification. The first three members of this structure contain input values supplied by PoFx. The last two members contain output values that the PEP writes to the structure in response to this notification.

The <b>Register</b> member contains a pointer to an input buffer allocated by PoFx. PoFx writes the <a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a> structure and associated data to this structure before sending the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification to the PEP. The contents of this buffer remain valid only until the PEP finishes handling the notification and returns from the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186626">AcceptDeviceNotification</a> callback.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186626">AcceptDeviceNotification</a>



<a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a>



<a href="..\pepfx\ne-pepfx-_pep_device_acceptance_type.md">PEP_DEVICE_ACCEPTANCE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_REGISTER_DEVICE_V2 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

