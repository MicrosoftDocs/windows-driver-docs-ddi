---
UID: NE:wudfddi._DEVICE_POWER_STATE
title: "_DEVICE_POWER_STATE"
author: windows-driver-content
description: The DEVICE_POWER_STATE enumeration identifies the device power states that a device can enter.
old-location: wdf\device_power_state.htm
old-project: wdf
ms.assetid: 7dd4d0ae-876a-4156-8a09-2ebc82a25117
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DEVICE_POWER_STATE, _DEVICE_POWER_STATE, PowerDeviceD3, wudfddi/PowerDeviceD3, PDEVICE_POWER_STATE enumeration pointer, wudfddi/PowerDeviceD0, PowerDeviceD0, wudfddi/DEVICE_POWER_STATE, wudfddi/PowerDeviceD1, wudfddi/PDEVICE_POWER_STATE, PowerDeviceD1, wudfddi/PowerDeviceMaximum, DEVICE_POWER_STATE enumeration, umdf.device_power_state, PowerDeviceD2, PowerDeviceMaximum, wdf.device_power_state, umdfstructs_6dca1ebb-421e-446b-b2b6-cc7b87afcf58.xml, PowerDeviceUnspecified, wudfddi/PowerDeviceUnspecified, PDEVICE_POWER_STATE, wudfddi/PowerDeviceD2, *PDEVICE_POWER_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi.h
apiname:
-	DEVICE_POWER_STATE
product: Windows
targetos: Windows
req.typenames: DEVICE_POWER_STATE, *PDEVICE_POWER_STATE
req.product: Windows 10 or later.
---

# _DEVICE_POWER_STATE enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>DEVICE_POWER_STATE</b> enumeration identifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">device power states</a> that a device can enter.


## -syntax


````
typedef enum _DEVICE_POWER_STATE { 
  PowerDeviceUnspecified  = 0,
  PowerDeviceD0           = ( PowerDeviceUnspecified + 1 ),
  PowerDeviceD1           = ( PowerDeviceD0 + 1 ),
  PowerDeviceD2           = ( PowerDeviceD1 + 1 ),
  PowerDeviceD3           = ( PowerDeviceD2 + 1 ),
  PowerDeviceMaximum      = ( PowerDeviceD3 + 1 )
} DEVICE_POWER_STATE, *PDEVICE_POWER_STATE;
````


## -enum-fields




### -field PowerDeviceUnspecified

The device power state is unspecified.


### -field PowerDeviceD0

The device's working (D0) state. This is the device's highest power state.


### -field PowerDeviceD1

The device's D1 <a href="https://msdn.microsoft.com/f594a63f-10ce-439d-abe3-d342555d98f0">sleeping state</a>.


### -field PowerDeviceD2

The device's D2 sleeping state.


### -field PowerDeviceD3

The device's D3 sleeping state.


### -field PowerDeviceMaximum

For system use only.


## -remarks


The <b>DEVICE_POWER_STATE</b> enumeration is used as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556920">IWDFDevice2::AssignS0IdleSettings</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556923">IWDFDevice2::AssignSxWakeSettings</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556920">IWDFDevice2::AssignS0IdleSettings</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556923">IWDFDevice2::AssignSxWakeSettings</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20DEVICE_POWER_STATE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

