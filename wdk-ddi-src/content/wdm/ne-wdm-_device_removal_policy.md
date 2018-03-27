---
UID: NE:wdm._DEVICE_REMOVAL_POLICY
title: "_DEVICE_REMOVAL_POLICY"
author: windows-driver-content
description: The DEVICE_REMOVAL_POLICY enumeration describes a device's removal policy.
old-location: kernel\device_removal_policy.htm
old-project: kernel
ms.assetid: 51d1f0f5-4ca1-4ea6-8561-117240551355
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PDEVICE_REMOVAL_POLICY, DEVICE_REMOVAL_POLICY, DEVICE_REMOVAL_POLICY enumeration [Kernel-Mode Driver Architecture], PDEVICE_REMOVAL_POLICY, PDEVICE_REMOVAL_POLICY enumeration pointer [Kernel-Mode Driver Architecture], RemovalPolicyExpectNoRemoval, RemovalPolicyExpectOrderlyRemoval, RemovalPolicyExpectSurpriseRemoval, _DEVICE_REMOVAL_POLICY, kernel.device_removal_policy, sysenum_46a08528-1177-4dd0-933f-6c4d7aa6c5b3.xml, wdm/DEVICE_REMOVAL_POLICY, wdm/PDEVICE_REMOVAL_POLICY, wdm/RemovalPolicyExpectNoRemoval, wdm/RemovalPolicyExpectOrderlyRemoval, wdm/RemovalPolicyExpectSurpriseRemoval"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	Wdm.h
api_name:
-	DEVICE_REMOVAL_POLICY
product: Windows
targetos: Windows
req.typenames: DEVICE_REMOVAL_POLICY, *PDEVICE_REMOVAL_POLICY
req.product: Windows 10 or later.
---

# _DEVICE_REMOVAL_POLICY enumeration


## -description


The <b>DEVICE_REMOVAL_POLICY</b> enumeration describes a device's removal policy.


## -enum-fields




### -field RemovalPolicyExpectNoRemoval

The device is not typically removed.


### -field RemovalPolicyExpectOrderlyRemoval

The device is typically removed in an orderly fashion. (Before the device is removed, the Plug and Play [PnP] manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551705">IRP_MN_QUERY_REMOVE_DEVICE</a> request to the device's driver.)


### -field RemovalPolicyExpectSurpriseRemoval

The device can be removed suddenly. (The driver receives no advance warning that the device will be removed. The Plug and Play [PnP] manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> request when the device is removed.) 


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff549203">IoGetDeviceProperty</a> routine supplies a <b>DEVICE_REMOVAL_POLICY</b> enumeration value when a driver requests <b>DevicePropertyRemovalPolicy</b>. The operating system uses the value as a hint as to how the device is typically removed from the computer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551705">IRP_MN_QUERY_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549203">IoGetDeviceProperty</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_REMOVAL_POLICY enumeration%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

