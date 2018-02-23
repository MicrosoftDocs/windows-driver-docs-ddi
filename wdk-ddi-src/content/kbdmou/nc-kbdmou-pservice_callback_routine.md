---
UID: NC:kbdmou.PSERVICE_CALLBACK_ROUTINE
title: PSERVICE_CALLBACK_ROUTINE
author: windows-driver-content
description: A function driver calls the class service callback in its ISR dispatch completion routine. The class service callback transfers input data from the input data buffer of a device to the class data queue.
old-location: hid\kbdclass_class_service_callback_routine.htm
old-project: hid
ms.assetid: 78ae2a98-bebd-43ee-b016-2f619c3135ca
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: hid.kbdclass_class_service_callback_routine, ClassServiceCallback callback function [Human Input Devices], ClassServiceCallback, PSERVICE_CALLBACK_ROUTINE, PSERVICE_CALLBACK_ROUTINE, kbdmou/ClassServiceCallback, kref_c3fa9125-0bc4-4936-b4e5-eb4e5eee23e2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: kbdmou.h
req.include-header: 
req.target-type: Desktop
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	kbdmou.h
apiname:
-	ClassServiceCallback
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_SessionStatistics, MSiSCSI_SessionStatistics"
---

# PSERVICE_CALLBACK_ROUTINE callback


## -description


A function driver calls the class service callback in its ISR dispatch completion routine. The class service callback transfers input data from the input data buffer of a device to the class data queue. 


## -prototype


````
PSERVICE_CALLBACK_ROUTINE ClassServiceCallback;

VOID ClassServiceCallback(
  _In_    PVOID NormalContext,
  _In_    PVOID SystemArgument1,
  _In_    PVOID SystemArgument2,
  _Inout_ PVOID SystemArgument3
)
{ ... }
````


## -parameters




### -param NormalContext [in]

Pointer to the class device object.


### -param SystemArgument1 [in]

Pointer to the first keyboard input data packet in the input data buffer of the port device.


### -param SystemArgument2 [in]

Pointer to the keyboard input data packet that immediately follows the last data packet in the input data buffer of the port device.


### -param SystemArgument3 [in, out]

Pointer to the number of keyboard input data packets that are transferred by the routine.


## -returns



This callback function does not return a value.




## -remarks



<b>Keyboard Class Service Callback</b>

Here is the definition of the  keyboard class service callback routine.

Kbdclass uses an <a href="..\kbdmou\ni-kbdmou-ioctl_internal_keyboard_connect.md">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request to connect its class service callback to a keyboard device. In this call, the driver sets  its implementation in a <a href="..\kbdmou\ns-kbdmou-_connect_data.md">CONNECT_DATA</a> structure.

<pre class="syntax" xml:space="preserve"><code>
/*
DeviceObject [in] 
Pointer to the class device object.

InputDataStart [in] 
Pointer to the first keyboard input data packet in the input data buffer of the port device.

InputDataEnd [in] 
Pointer to the keyboard input data packet that immediately follows the last data packet in the input data buffer of the port device.

InputDataConsumed [in, out] 
Pointer to the number of keyboard input data packets that are transferred by the routine.

*/
VOID KeyboardClassServiceCallback(
  _In_    PDEVICE_OBJECT       DeviceObject,
  _In_    PKEYBOARD_INPUT_DATA InputDataStart,
  _In_    PKEYBOARD_INPUT_DATA InputDataEnd,
  _Inout_ PULONG               InputDataConsumed
);
</code></pre>
<b>KeyboardClassServiceCallback</b> transfers input data from the input buffer of the device to the class data queue. This routine is called by the ISR dispatch completion routine of the function driver.

<b>KeyboardClassServiceCallback</b> can be supplemented by a filter service callback that is provided by an upper-level keyboard filter driver. A filter service callback filters the keyboard data that is transferred to the class data queue. For example, the filter service callback can delete, transform, or insert data. <a href="http://go.microsoft.com/fwlink/p/?linkid=256125">Kbfiltr</a>, the sample filter driver in code gallery, includes <b>KbFilter_ServiceCallback</b>, which is a template for a keyboard filter service callback.

<b>Mouse Class Service Callback</b>

Here is the <b>MouseClassServiceCallback</b> routine is the class service callback routine that is provided by Mouclass. The driver uses an <a href="..\kbdmou\ni-kbdmou-ioctl_internal_mouse_connect.md">IOCTL_INTERNAL_MOUSE_CONNECT</a> request to connect its class service callback to a mouse device. In this call, the driver sets  its implementation in a <a href="..\kbdmou\ns-kbdmou-_connect_data.md">CONNECT_DATA</a> structure.


<pre class="syntax" xml:space="preserve"><code>
/*
DeviceObject [in] 
Pointer to the class device object.

InputDataStart [in] 
Pointer to the first mouse input data packet in the input buffer of the port device.

InputDataEnd [in] 
Pointer to the mouse input data packet that immediately follows the last data packet in the input data buffer of the port device.

InputDataConsumed [in, out] 
Pointer to the number of mouse input data packets that are transferred by the routine.

*/
VOID MouseClassServiceCallback(
  _In_    PDEVICE_OBJECT    DeviceObject,
  _In_    PMOUSE_INPUT_DATA InputDataStart,
  _In_    PMOUSE_INPUT_DATA InputDataEnd,
  _Inout_ PULONG            InputDataConsumed
);
);
</code></pre>


<b>MouseClassServiceCallback</b> transfers input data from the input buffer of the device to the class data queue. This routine is called by the ISR dispatch completion routine of the function driver.

<b>MouseClassServiceCallback</b> can be supplemented by a filter service callback that is provided by an upper-level mouse filter driver. A filter service callback can filter the mouse data that is transferred to the class data queue. For example, the filter service callback can delete, transform, or insert data. <a href="http://go.microsoft.com/fwlink/p/?linkid=256135">Moufiltr</a>, the sample filter driver in the WDK, includes <b>MouFilter_ServiceCallback</b>, which is a template for a filter service callback.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542337">KEYBOARD_INPUT_DATA</a>



<a href="..\kbdmou\ns-kbdmou-_connect_data.md">CONNECT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542403">MOUSE_INPUT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20PSERVICE_CALLBACK_ROUTINE callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

