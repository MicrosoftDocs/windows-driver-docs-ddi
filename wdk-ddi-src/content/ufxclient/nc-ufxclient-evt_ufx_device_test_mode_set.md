---
UID: NC:ufxclient.EVT_UFX_DEVICE_TEST_MODE_SET
title: EVT_UFX_DEVICE_TEST_MODE_SET
author: windows-driver-content
description: The client driver's implementation to set the test mode of the function controller.
old-location: buses\evt_ufx_device_test_mode_set.htm
old-project: usbref
ms.assetid: 24B17B8E-C2F0-4CA8-AA9D-5EE86EB20CCC
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ufx_device_test_mode_set, EvtUfxDeviceTestModeSet callback function [Buses], EvtUfxDeviceTestModeSet, EVT_UFX_DEVICE_TEST_MODE_SET, EVT_UFX_DEVICE_TEST_MODE_SET, ufxclient/EvtUfxDeviceTestModeSet, PFN_UFX_DEVICE_TEST_MODE_SET callback function pointer [Buses], PFN_UFX_DEVICE_TEST_MODE_SET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Ufxclient.h
apiname: 
-	PFN_UFX_DEVICE_TEST_MODE_SET
product: Windows
targetos: Windows
req.typenames: *PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# EVT_UFX_DEVICE_TEST_MODE_SET callback


## -description


The client driver's implementation to set the test mode of the function controller.


## -prototype


````
EVT_UFX_DEVICE_TEST_MODE_SET EvtUfxDeviceTestModeSet;

void EvtUfxDeviceTestModeSet(
  _In_ UFXDEVICE UfxDevice,
  _In_ ULONG     TestMode
)
{ ... }

typedef EVT_UFX_DEVICE_TEST_MODE_SET PFN_UFX_DEVICE_TEST_MODE_SET;
````


## -parameters










#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


#### - TestMode [in]

Test mode selector value as defined by the USB 2.0 Specification.  These values are defined in usbfnbase.h
<ul>
<li>USB_TEST_MODE_TEST_J              0x01</li>
<li>USB_TEST_MODE_TEST_K              0x02
</li>
<li>USB_TEST_MODE_TEST_SE0_NAK        0x03
</li>
<li>USB_TEST_MODE_TEST_PACKET         0x04
</li>
<li>USB_TEST_MODE_TEST_FORCE_ENABLE   0x05
</li>
</ul>

## -returns


This callback function does not return a value.



## -remarks


The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_TEST_MODE_SET</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a> method.



## -see-also

<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>

<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_TEST_MODE_SET callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

