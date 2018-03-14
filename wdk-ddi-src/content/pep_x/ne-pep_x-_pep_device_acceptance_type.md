---
UID: NE:pep_x._PEP_DEVICE_ACCEPTANCE_TYPE
title: "_PEP_DEVICE_ACCEPTANCE_TYPE"
author: windows-driver-content
description: The PEP_DEVICE_ACCEPTANCE_TYPE enumeration indicates whether a PEP accepts ownership of a device.
old-location: kernel\pep_device_acceptance_type.htm
old-project: kernel
ms.assetid: 72D0BEC2-F5D5-4045-AD63-F263993817B0
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_DEVICE_ACCEPTANCE_TYPE, PEP_DEVICE_ACCEPTANCE_TYPE, PEP_DEVICE_ACCEPTANCE_TYPE enumeration [Kernel-Mode Driver Architecture], PepDeviceAccepted, PepDeviceAcceptedMax, PepDeviceAcceptedReserved, PepDeviceNotAccepted, _PEP_DEVICE_ACCEPTANCE_TYPE, kernel.pep_device_acceptance_type, pepfx/PEP_DEVICE_ACCEPTANCE_TYPE, pepfx/PepDeviceAccepted, pepfx/PepDeviceAcceptedMax, pepfx/PepDeviceAcceptedReserved, pepfx/PepDeviceNotAccepted"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_DEVICE_ACCEPTANCE_TYPE
product: Windows
targetos: Windows
req.typenames: PEP_DEVICE_ACCEPTANCE_TYPE, *PPEP_DEVICE_ACCEPTANCE_TYPE, PEP_DEVICE_ACCEPTANCE_TYPE, *PPEP_DEVICE_ACCEPTANCE_TYPE
---

# _PEP_DEVICE_ACCEPTANCE_TYPE enumeration


## -description


The <b>PEP_DEVICE_ACCEPTANCE_TYPE</b> enumeration indicates whether a PEP accepts ownership of a device.


## -syntax


````
typedef enum _PEP_DEVICE_ACCEPTANCE_TYPE { 
  PepDeviceNotAccepted       = 0,
  PepDeviceAcceptedReserved,
  PepDeviceAccepted,
  PepDeviceAcceptedMax
} PEP_DEVICE_ACCEPTANCE_TYPE;
````


## -enum-fields




### -field PepDeviceNotAccepted

The PEP does not claim ownership of this device.


### -field PepDeviceAccepted

The PEP claims ownership of this device.


### -field PepDeviceAceptedMax




#### - PepDeviceAcceptedMax

Reserved for use by operating system.


#### - PepDeviceAcceptedReserved

The PEP claims ownership of the device on behalf of the default PEP. The default PEP is implemented by the Windows kernel to manage devices for which hardware-specific PEPs are not available.


## -remarks



This enumeration is used by <b>DeviceAccepted</b> member of the <a href="..\pepfx\ns-pepfx-_pep_register_device_v2.md">PEP_REGISTER_DEVICE_V2</a> structure to indicate whether a PEP accepts ownership of a device.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_register_device_v2.md">PEP_REGISTER_DEVICE_V2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_DEVICE_ACCEPTANCE_TYPE enumeration%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

